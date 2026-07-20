# Sessao-03
Configuração de uma política defensiva estrita para impedir acessos não autorizados a serviços críticos do servidor, combinando UFW e iptables.


**Sessão Laboratorial:** 03 - Hardening de Redes Linux e Configuração de Firewalls

---

## Contexto: 

Conﬁguração de uma política defensiva estrita para impedir acessos não autorizados a serviços críticos do servidor, combinando UFW e iptables.

## Tarefa a executar:

## a) Veriﬁcar o estado atual do UFW: sudo ufw status

<img width="346" height="96" alt="Captura de ecrã 2026-07-20 183116" src="https://github.com/user-attachments/assets/be5caee7-32cd-40e4-afe7-0714075884ba" />

## b) Alterar as políticas padrão — bloquear entrada, permitir saída:

*   **sudo ufw default deny incoming**

Bloqueia TODAS as ligações de entrada

root@ubuntu:~$ sudo ufw default deny incoming

Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)

* **sudo ufw default allow outgoing**

Permite todas as ligações de saída

root@ubuntu:~$ sudo ufw default allow outgoing

Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)

## c) Criar uma regra específica para permitir acesso SSH apenas na porta padrão:

sudo ufw allow 22/tcp

root@ubuntu:~$ sudo ufw allow 22/tcp

Rule added

Rule added (v6)

## d)	Simular o bloqueio de um IP malicioso fictício na chain INPUT do iptables:
