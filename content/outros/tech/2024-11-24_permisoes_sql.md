+++
title = 'Tech nerd: permissões SQL'
date = 2024-11-24T10:27:29-03:00
tags = ['sql', 'linux']
+++

## Permissões SQL Postgres

Passando aqui para deixar registrado uma dica rápida.

Uma das coisas que estava me desanimando a aprender [POSTGRESQL](https://www.postgresql.org/) era a dificuldade com:
1. acessar o banco de dados em primeiro lugar, usando o [pgadmin](https://www.pgadmin.org/)
2. conseguir copiar qualquer arquivo para o banco de dados

O Linux usa um sistema de permissões bem amarrado e, como o postgres usa um usuário diferente do meu usuário por padrão, estava bem chato de entender toda essa relação de usuários e permissões.

a situação número 1. eu consegui resolver editando o arquivo /var/lib/pgsql/data/pg_hba.conf e trocando o  método de autenticação de `ident`  para `password` nas 3 primeiras conexões locais.

a situação 2. eu protelei mais para resolver e fui me virando salvando os arquivos na pasta /var/lib/pgsql/ que claramente não era o ideal.

Tentei usar a pasta /tmp para esse fim, mas recebia um erro toda hora de um serviço chamado [SElinux](https://www.redhat.com/pt-br/topics/linux/what-is-selinux). Hoje, resolvi tentar novamente e achei em algum lugar que sugeria simplesmente desabilitar esse serviço SElinux, que eu nem sabia que era um serviço opcional. Enfim, desabilitei editando o arquivo de config que estava /etc/selinux/config e agora as coisas parecem mais suaves. O primeiro teste eu ainda fiz com um arquivo criado pelo usuário postgres, no próximo vou tentar com meu usuário padrão, vamos ver se vai.
 


