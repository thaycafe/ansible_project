## My Ansible Project

Este projeto contém uma receita completa para a instalação do endpoint MinIO Uploader. A receita foi construída através da ferramenta de automação [Ansible](https://docs.ansible.com/).

### Instalação
------------
[Neste](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) guia você vai encontrar como instalá-lo em sua distribuição.

### Árvore do projeto
------------
```bash
├── main.yml
├── README.md
├── roles
│   ├── gunicorn
│   │   └── tasks
│   │       └── main.yml
│   ├── minio
│   │   └── tasks
│   │       └── main.yml
│   └── project
│       └── tasks
│           └── main.yml
└── vars
    └── vault.yml
```

### Inventório
------------
Você irá precisar criar um arquivo `hosts` para definir os servidores em que o [Ansible](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html) irá executar a automação. Exemplo:

```bash
ip.address

[groupname]
foo.example.com
bar.example.com
```

### Variáveis
------------
As variáres do repositório estão criptografadas com o [Ansible Vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html). Estão localizadas em `vars/vault.yml` , caso você tenha acesso e queira visualizar basta executar:

```ansible-vault view vars/vault.yml```

### Execução
------------
Com o inventório devidamente criado, você está pronto para executar a ferramenta. Na pasta raiz você irá executar o principal [Playbook](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html) `main.yml`. Exemplo:

```ansible-playbook -i hosts --ask-pass main.yml```

### Repositório do Minio Uploader com Gitlab CI/CD
[Minio Uploader](https://gitlab.com/thaygneel/minio-uploader)
