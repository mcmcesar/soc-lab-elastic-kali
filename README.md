k#!/bin/bash
set -e

echo "[*] Entrando na pasta do projeto..."
cd ~/soc-lab-elastic-kali

echo "[*] Escrevendo README.md completo..."
cat > README.md << 'README_CONTENT'
# 🛡️ Enterprise SOC & Threat Simulation Laboratory

Laboratório prático de Segurança Defensiva (Blue Team / SOC Nível 1) projetado para simular uma infraestrutura corporativa segmentada, canal de acesso seguro via VPN criptografada e monitoramento de eventos de autenticação através do Elastic Stack 8.x.

---

## 📐 Topologia de Rede do Laboratório

```text
       [ Atacante / Analista SOC ]
             Kali Linux
         eth1: 198.51.100.2/24
                   │
                   ▼ (Tráfego WAN Simulado)
         [ Debian-Router / Firewall ]
           enp0s3: 198.51.100.1/24 (Borda)
           enp0s8: 192.168.50.1/24  (Gateway LAN)
                   │
                   ▼ (Rede Interna Isolada)
         [ Debian Servidor / SIEM ]
           enp0s3: 192.168.50.10/24 (LAN)
           
  ══════════════════════════════════════════════════════
    Túnel Criptografado WireGuard (wg0: 10.66.0.0/24)
    Kali (10.66.0.2) ──[Encapsulado]──> Servidor (10.66.0.1)
  ══════════════════════════════════════════════════════
```

---

## 🛠️ Tecnologias e Ferramentas Empregadas

* **Virtualizacao:** VirtualBox 7.x (Redes Internas e Host-Only)
* **Firewall / Roteamento:** Debian GNU/Linux com nftables (Políticas restritivas de DROP e encaminhamento)
* **Túnel VPN:** WireGuard (Criptografia de chave pública Curve25519)
* **SIEM & Telemetria:** Elasticsearch 8.x, Kibana e Filebeat (Módulo System / auth.log)
* **Simulacao de Ameaça:** Kali Linux com THC-Hydra

---

## 📸 Evidências Técnicas de Implementação

### 1. Configuração de Interfaces de Rede
Configuração da interface WAN física e ativação da interface wg0 encapsulada.
![Topologia de Interfaces](docs/images/01_topologia_interfaces.png)

### 2. Túnel Criptografado WireGuard
Validação de handshake ativo, persistência de conexão (keepalive) e tráfego de dados bidirecional.
![Handshake WireGuard](docs/images/02_wireguard_handshake.png)

### 3. Ingestão de Telemetria no Elastic SIEM (Kibana)
Painel do Discover exibindo os eventos indexados pelo agente Filebeat através do canal seguro.
![Kibana Discover](docs/images/03_kibana_discover_geral.png)

### 4. Simulação de Ataque de Força Bruta (SSH)
Execução de ataque de dicionário com Hydra contra o serviço SSH exposto no túnel (`10.66.0.1:22`).
![Simulação Hydra](docs/images/04_hydra_attack_simulation.png)

### 5. Análise Granular de Logs de Autenticação
Registros de eventos detalhados capturados no cluster do Elasticsearch.
![Tabela de Logs](docs/images/05_elastic_logs_tabela.png)

---

## 🎯 Regra de Detecção KQL Aplicada no SIEM

```kql
event.category: "authentication" and event.outcome: "failure" and service.type: "ssh"
```

* **Tipo de Regra:** Threshold (Limite de tentativas)
* **Critério de Disparo:** Mais de 5 falhas consecutivas no intervalo de 1 minuto agrupadas pelo campo `source.ip`.
* **Severidade:** Alta (High) | **Risk Score:** 73
README_CONTENT

echo "[*] Criando .gitignore de seguranca..."
cat > .gitignore << 'GITIGNORE_CONTENT'
*.tmp
*.log
passwords.txt
/tmp/
privatekey*
client_priv
server_priv
GITIGNORE_CONTENT

echo "[*] Indexando arquivos no Git..."
git config --global user.name "mcmcesar"
git config --global user.email "mciadss@gmail.com"
git add README.md .gitignore docs/images/*.png

echo "[*] Criando commit..."
git commit -m "feat: documentacao completa e evidencias do lab SOC"

echo "[*] Atualizando remote origin..."
git remote remove origin 2>/dev/null || true
git remote add origin https://github.com/mcmcesar/soc-lab-elastic-kali.git

echo "[*] Enviando tudo para o GitHub..."
git push -u origin main --force

echo "[✔] Concluído com sucesso! Acesse: https://github.com/mcmcesar/soc-lab-elastic-kali"
