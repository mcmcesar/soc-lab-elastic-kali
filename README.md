# 🛡️ SOC Lab: Detecção, Resposta a Incidentes & Conectividade Zero Trust

[![Status](https://img.shields.io/badge/Status-Concluído-success.svg)]()
[![SIEM](https://img.shields.io/badge/SIEM-Elasticsearch%208.x-blue.svg)]()
[![VPN](https://img.shields.io/badge/VPN-WireGuard%20Zero%20Trust-orange.svg)]()

> **Analista:** Marcos César Inácio da Luz  
> **Cenário:** Simulação de ataque de força bruta SSH, triagem de logs com Elastic Stack e isolamento de tráfego administrativo via túnel WireGuard.

---

## 🖥️ Topologia e Conectividade

* **Servidor Central (Debian 13):** IP Físico `10.10.17.18` | IP Seguro VPN `10.66.0.1`
* **Estação de Teste / Atacante (Kali):** IP Físico `10.10.17.15` | IP Seguro VPN `10.66.0.2`
* **Camada de Criptografia:** WireGuard (UDP 51820 / ChaCha20-Poly1305)

---

## ⚡ Fluxo Operacional de SOC N1

1. **Simulação:** Execução de força bruta com Hydra contra a porta 22 (`ssh`).
2. **Ingestão:** Filebeat coletando `/var/log/auth.log` e transmitindo para o Elasticsearch.
3. **Triagem (KQL):** 
   ```kql
   event.dataset: "system.auth" and event.outcome: "failure"
