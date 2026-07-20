# Samba Lab

Laboratório de implementação e administração de um servidor Samba em ambiente Linux, com foco em compartilhamento de arquivos, gerenciamento de usuários e controle de permissões.

---

## Objetivos

- Instalar e configurar o Samba no AlmaLinux 9.
- Criar compartilhamentos de rede.
- Gerenciar usuários e grupos.
- Configurar permissões de acesso.
- Validar o acesso a partir de clientes Linux.
- Documentar todas as etapas de configuração.

---

## Ambiente

| Item | Descrição |
|------|-----------|
| Sistema Operacional | AlmaLinux 9 |
| Serviço | Samba |
| Cliente | Linux |
| Protocolo | SMB/CIFS |

---

## Funcionalidades

- Compartilhamento de arquivos.
- Controle de permissões.
- Autenticação por usuários locais.
- Testes de conectividade.
- Administração do serviço Samba.

---

## Tecnologias

- AlmaLinux 9
- Samba
- Systemd
- Bash
- SMB/CIFS

---

## Comandos Utilizados

```bash
dnf install samba samba-client

systemctl enable smb --now

systemctl status smb

testparm

smbclient -L localhost -U usuario
```

---

## Estrutura do Projeto

```
samba-lab/
├── README.md
├── docs/
├── configs/
├── scripts/
└── images/
```

---

## Próximas Etapas

- [ ] Configuração dos compartilhamentos.
- [ ] Criação de usuários Samba.
- [ ] Controle de acesso.
- [ ] Testes com clientes Linux.
- [ ] Documentação das configurações.
