
# MVP - Automação de Atualização de Servidores Linux RHEL

Este documento descreve os passos iniciais para um MVP (Minimum Viable Product) focado na atualização de servidores Linux RHEL 8 e 9. Este MVP é projetado como uma base para testes e melhorias iterativas. Todas as contribuições e colaborações são bem-vindas para aprimorar e expandir este projeto.

## Visão Geral

O objetivo deste MVP é estabelecer um procedimento automatizado para atualizar servidores Linux RHEL. A automação é realizada utilizando o Ansible, uma ferramenta poderosa e flexível para gerenciamento de configurações e automações.

## Pré-requisitos

- Servidores com RHEL 8 ou 9 configurados e acessíveis.
- Ansible instalado e configurado em uma máquina de controle.
- Acesso adequado aos servidores-alvo para a execução de comandos de atualização.


# Configuração Básica do Ansible Automation Platform (AAP)

## Credenciais

### Criar Credencial do Automation Controller
- **Path**: `Resources > Credential > Add`
- **Nome**: CRED-AC-CONFIG
- **Descrição**: Credencial de configuração do Automation Controller
- **Organização**: SECURITY ou Defaults
- **Tipo de Credencial**: Red Hat Ansible Automation Platform
- **Hostname/IP**: [Endereço do Automation Controller]
- **Username**: admin
- **Password**: [Senha]

### Criar Credencial do Git Interno
- **Path**: `Resources > Credential > Add`
- **Nome**: CRED-GIT-INTERNAL ou CRED-GIT-TEST
- **Descrição**: Credenciais de acesso ao Git interno
- **Organização**: SECURITY ou Defaults
- **Tipo de Credencial**: Source Control
- **Username e Password**: [Detalhes de acesso]

## Projetos

### Criar Projeto/Repositório de Código de Automação
- **Path**: `Resources > Projects > Add`
- **Nome**: PROJ-GIT-UPDATEFIX
- **Descrição**: Repositório de automações para update de servidores Linux
- **Organização**: SECURITY ou Defaults
- **Ambiente de Execução**: Default execution environment
- **Tipo de Controle de Fonte**: Git
- **URL do Controle de Fonte**: [URL do repositório Git]
- **Credencial do Controle de Fonte**: [Selecione a credencial criada]

## Inventário

### Criar Inventário de Hosts
- **Path**: `Resources > Inventory > Add`
- **Nome**: INV-AC
- **Descrição**: Inventário do Automation Controller
- **Organização**: SECURITY ou Defaults
- **Labels**: ac

### Adicionar Hosts no Inventário
- **Nome**: [Hostname ou IP do host]
- **Descrição**: [Detalhes do host]

## Job Template

### Criar um Job Template
- **Path**: `Resources > Templates > Add > Add job template`
- **Nome**: CONFIG-AC-BASE
- **Descrição**: Configuração básica do AAP
- **Tipo de Trabalho**: Run
- **Inventário**: INV-AC
- **Projeto**: PROJ-GIT-UPDATEFIX
- **Ambiente de Execução**: Default execution environment
- **Playbook**: [Nome do playbook]
- **Credenciais**: [Selecione CRED-AC-CONFIG]
- **Labels**: ac

Para mais informações, consulte o [Ansible Automation Platform Administration Guide](https://access.redhat.com/documentation/en-us/red_hat_ansible_automation_platform/).
