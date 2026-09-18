# 🛡️ SOC Lab: Detecção, Análise e Resposta a Incidentes (Elastic Stack & Kali Linux)

Projeto prático de simulação, monitoramento, investigação e contenção de incidentes de segurança cibernética em ambiente local, reproduzindo a rotina de um Analista de SOC N1.

---

## Visão Geral do Cenário

* Servidor de Monitoramento / Alvo: Debian GNU/Linux 13 (Trixie) - IP 10.10.17.16
* Estação de Ataque: Kali Linux - IP 10.10.17.13
* Stack SIEM & Coleta: Elasticsearch 8.x, Kibana e Filebeat

O objetivo foi simular um ataque automatizado de força bruta via SSH, identificar o evento em tempo real via logs do sistema (auth.log), realizar a triagem técnica no Kibana e executar a contenção no firewall de host.

---

## Simulação do Incidente

A partir do Kali Linux (10.10.17.13), executou-se um ataque de dicionário contra a porta 22 (SSH) do Debian (10.10.17.16):

hydra -l root -P senhas.txt -t 4 10.10.17.16 ssh

O ataque gerou múltiplas tentativas de autenticação inválidas em segundos, registradas pelo daemon SSH.

---

## Investigação e Triagem (Kibana KQL)

Filtro aplicado na interface Discover para isolar o ataque:

event.dataset: "system.auth" and event.outcome: "failure"

Evidências extraídas:
* Timestamp: 00:15:36 a 00:15:38
* IP Atacante (source.ip): 10.10.17.13
* Conta visada (user.name): root
* Detalhe: Falha de autenticação por senha para superusuário

---

## Ticket de Incidente (SOC N1)

* Incidente ID: INC-20260918-001
* Severidade: Média
* Vetor: Força Bruta via SSH (T1110 - MITRE ATT&CK)
* Alvo: 10.10.17.16:22 (Debian)
* Origem: 10.10.17.13 (Kali Linux)
* Status: Contido

---

## Contenção e Resposta Ativa

Bloqueio imediato aplicado na camada de rede com Netfilter/Iptables no Debian:

iptables -I INPUT -s 10.10.17.13 -j DROP

Resultado: novas tentativas com Hydra resultaram em timeout imediato, isolando o atacante.

---

## Recomendações de Mitigação

1. Desabilitar login direto de root no SSH (PermitRootLogin no).
2. Utilizar autenticação exclusiva por chave pública.
3. Configurar ferramentas de bloqueio automático como Fail2Ban.
4. Alterar a porta padrão do serviço SSH.
