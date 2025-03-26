# UpdateFix - Relatório de Atualização

## Data e Hora
- **Início do processo:** 2024-05-02 19:13:53
- **Hostname:** `web01.aroque.com.br`
- **Versão do UpdateFix:** `0010`

---
##  Informações do Servidor
| Propriedade           | Valor |
|-----------------------|---------------------------------|
| **Distribuição**     | RedHat |
| **Release**          | 9.3 |
| **Kernel**           | 5.14.0-362.24.1.el9_3.x86_64 |
| **SELinux**          | Enabled |
| **IPV4**             | 192.168.100.21 |
| **Arquitetura**      | x86_64 |
| **Virtual/Físico**   | KVM |
| **Uptime**           | 8 horas |
| **CPUs**             | 1 |
| **Memória**          | 0.75 GB |

---
## Validação dos Pré-requisitos

| Requisito                          | Status |
|-------------------------------------|--------|
| Espaço em disco `/`                | ✅ OK |
| Espaço em disco `/boot`            | ✅ OK |
| Filesystem `/` Read-only           | ✅ OK |
| Filesystem `/boot` Read-only       | ✅ OK |
| Subscrição                         | ✅ OK |
| Repositórios                       | ✅ OK |
| Pacotes duplicados                 | ✅ OK |
| Processos zumbis                   | ✅ OK |
| Serviços não persistentes          | ✅ OK |
| Serviços e processos Zabbix        | ✅ OK |
| MountPoint listados no `fstab`     | ✅ OK |
| MountPoint não listado no `fstab`  | ✅ OK |
| Validação de autenticação LDAP     | ⚠️ WARNING |
| Uptime/Reboot                      | ✅ OK |
| Host possui inventário             | ✅ OK |
| Acessível via Ansible              | ✅ OK |

### **Servidor pronto para update:** ✅ OK

---
## 📂 Pontos de Montagem
- **Logs de `/etc/fstab`**: Sem erros ou avisos detectados.
- **Pontos de montagem ativos NÃO especificados no `/etc/fstab`**: Nenhum.

---
## 🛠️ Serviços Listados Antes do Update
### **Ativos e habilitados:**
- `auditd.service`
- `chronyd.service`
- `crond.service`
- `dbus-broker.service`
- `firewalld.service`
- `httpd.service`
- `NetworkManager.service`
- `node_exporter.service`
- `qemu-guest-agent.service`
- `rhsm.service`
- `rhsmcertd.service`
- `rsyslog.service`
- `sshd.service`
- `zabbix-agent2.service`

### **Ativos e desabilitados:**
*(Nenhum listado)*

---
## Processos Listados Antes do Update
### **Top 10 Processos**
1. `root /usr/bin/python3`
2. `root /usr/bin/python3`
3. `root /usr/bin/python3`
4. `node_ex+ /usr/local/bin/node_exporter`
5. `root /usr/bin/python3`
6. `root /usr/bin/python3`
7. `root /usr/bin/python3`
8. `zabbix /usr/sbin/zabbix_agent2`
9. `root /usr/bin/python3`
10. `root /usr/sbin/NetworkManager`

### **Top 10 Processos Não Root**
1. `node_ex+ /usr/local/bin/node_exporter`
2. `zabbix /usr/sbin/zabbix_agent2`
3. `polkitd /usr/lib/polkit-1/polkitd`
4. `apache /usr/sbin/httpd`
5. `apache /usr/sbin/httpd`
6. `apache /usr/sbin/httpd`
7. `apache /usr/sbin/httpd`
8. `dbus /usr/bin/dbus-broker-launch`
9. `chrony /usr/sbin/chronyd`
10. `dbus dbus-broker`

---
## Primeiro Reboot
- **Horário:** 2024-05-02 19:14:57
- **Status:** Reboot realizado com sucesso!
- **Logs detalhados:** `/var/log/ansible/updatefix/updatefix_0010/primeiro_reboot_updatefix_0010.log`

---
## Informações Pré-Update
- Atualização dos repositórios realizada.
- **Última verificação de metadados:** 16 minutos atrás.

### Resumo das Atualizações Disponíveis
- **Notificações de Segurança:** 23
  - 🔴 4 **Importantes**
  - 🟠 16 **Moderadas**
  - 🟡 3 **Baixas**
- **Correções de bugs:** 79
- **Melhorias:** 4

## Segundo Reboot
- **Horário:** 2024-05-02 19:40:57
- **Status:** Reboot realizado com sucesso!
- **Logs detalhados:** `/var/log/ansible/updatefix/updatefix_0010/segundo_reboot_updatefix_0010.log`

---
✅ **UpdateFix concluído com sucesso!**
