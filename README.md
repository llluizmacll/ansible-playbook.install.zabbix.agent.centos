# ansible-playbook.install.zabbix.agent.centos
Repositório dedicado para automatização do agent do zabbix no centos, utilizando Ansible.
├── main.yml                                >> Chama as tarefas
├── README.md
└── roles                                   >> Estrutura do Ansible
    ├── files                               >> Arquivos/Pacotes
    │   ├── zabbix_agentd.conf
    │   └── zabbix-api-0.5.3.tar.gz
    └── tasks                               >> Tarefas
        ├── agent-zabbix.yml
        └── main.yml                        >> Chama as tarefas
