# ansible-zabbix-agent
Repositório dedicado para automatização do agent do zabbix, utilizando Ansible.

## Estrutura do repositório:

```
├── main.yml                                >> Chama as tarefas
├── README.md
└── roles                                   >> Estrutura do Ansible
    ├── files                               >> Arquivos/Pacotes
    │   ├── zabbix_agentd.conf
    │   
    └── tasks                               >> Tarefas
        ├── agent-zabbix.yml
        └── main.yml                        >> Chama as tarefas
```

## Como utilizar?
Primeiro iremos clonar o repositório.

```
$ git clone https://github.com/llluizmacll/ansible-playbook.install.zabbix.agent.centos.git
```
Após clonar o repositório ajuste os parâmetros do arquivo playbook e arquivo de configuração com as informações do seu zabbix server, esses arquivos são: zabbix_agentd.conf e agent-zabbix.yml.

Crie um grupo de hosts com o servidores que deseja instalar o agente, o arquivo fica localizado em /etc/ansible/hosts

Ex de criação de grupo de host:

[serverlinux]

tldapp01 ansible_ssh_host=10.100.12.28 ansible_ssh_user=root
zabbix_server_hom ansible_ssh_host=10.100.19.112 ansible_ssh_user=root

## Executando playbook

Ao executar o playbook iremos chamar setar o arquivo main, arquivo que chama as tasks e em extra-vars colocar o grupo ou nome do host que você definiu no seu arquivo de hosts do Ansible.

```
$ cd ansible-zabbix-agent

$ ansible-playbook main.yml --extra-vars "hosts=grupodehosts"
```

Após executar o seu playbook, basta ir no fontend do zabbix e conferir o host lá! ;)  

