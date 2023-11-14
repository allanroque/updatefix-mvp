
Configuração Básica do Ansible Automation Platform (AAP)
Credenciais
No AAP, as credenciais são usadas para autenticar e autorizar acessos a diferentes sistemas e serviços. Elas são armazenadas de forma segura e podem ser reutilizadas em várias automações.

Criar Credencial do Automation Controller
Path: Resources > Credential > Add
Detalhes:
Nome: CRED-AC-CONFIG
Descrição: Credencial de configuração do Automation Controller
Organização: SECURITY ou Defaults
Tipo de Credencial: Red Hat Ansible Automation Platform
Hostname/IP: Endereço do Automation Controller
Username: admin
Password: [Senha]
Criar Credencial do Git Interno
Path: Resources > Credential > Add
Detalhes:
Nome: CRED-GIT-INTERNAL ou CRED-GIT-TEST
Descrição: Credenciais de acesso ao Git interno
Organização: SECURITY ou Defaults
Tipo de Credencial: Source Control
Username e Password: [Detalhes de acesso]
Projetos
Projetos no AAP representam coleções de playbooks e outros arquivos necessários para a execução de tarefas de automação.

Criar Projeto/Repositório de Código de Automação
Path: Resources > Projects > Add
Detalhes:
Nome: PROJ-GIT-UPDATEFIX
Descrição: Repositório de automações para update de servidores Linux
Organização: SECURITY ou Defaults
Ambiente de Execução: Default execution environment
Tipo de Controle de Fonte: Git
URL do Controle de Fonte: [URL do repositório Git]
Credencial do Controle de Fonte: [Selecione a credencial criada]
Inventário
Inventários no AAP são listas de hosts sobre os quais as automações serão executadas.

Criar Inventário de Hosts
Path: Resources > Inventory > Add
Detalhes:
Nome: INV-AC
Descrição: Inventário do Automation Controller
Organização: SECURITY ou Defaults
Labels: ac
Adicionar Hosts no Inventário
Detalhes:
Nome: [Hostname ou IP do host]
Descrição: [Detalhes do host]
Job Template
Um job template no AAP define uma série de parâmetros para executar uma tarefa, como o playbook a ser usado, credenciais, inventário, etc.

Criar um Job Template
Path: Resources > Templates > Add > Add job template
Detalhes:
Nome: CONFIG-AC-BASE
Descrição: Configuração básica do AAP
Tipo de Trabalho: Run
Inventário: INV-AC
Projeto: PROJ-GIT-UPDATEFIX
Ambiente de Execução: Default execution environment
Playbook: [Nome do playbook]
Credenciais: [Selecione CRED-AC-CONFIG]
Labels: ac
Para informações mais detalhadas e diretrizes específicas, consulte o Ansible Automation Platform Administration Guide.