# Atividade prática individual - Tópico 3

## Nível realizado

Nível 3 - Avançado

## Objetivo

Criar e publicar um serviço web em ambiente Linux, utilizando WordPress com Apache, PHP e MariaDB.

## Ambiente utilizado

VPS Ubuntu 24.04 em ambiente cloud.

## Rota de publicação

WordPress com Apache.

## Ficheiros e componentes utilizados

- Apache como servidor web
- PHP para execução da aplicação WordPress
- MariaDB como base de dados
- WordPress como aplicação web
- Pasta de publicação: `/var/www/html/topico-03-wordpress`

## URLs testados

- `http://<VPS_PUBLIC_IP>/topico-03-wordpress/`
- `http://<VPS_PUBLIC_IP>/topico-03-wordpress/wp-admin/`

## Evidências produzidas

As evidências foram guardadas na pasta `evidencias/`, incluindo:

- Validação do Apache
- Validação do PHP
- Validação do MariaDB
- Criação da base de dados WordPress
- Publicação dos ficheiros WordPress
- Permissões dos ficheiros
- Validação final do WordPress

## Dificuldades encontradas

Durante a atividade, foi identificado que o Nginx estava instalado e ativo na porta 80. Como a rota escolhida foi WordPress com Apache, foi necessário parar e desativar o Nginx para permitir que o Apache utilizasse a porta 80.

Também foi necessário separar a pasta do repositório GitHub da pasta real de publicação web. O repositório foi usado para documentação e evidências, enquanto o WordPress foi publicado em `/var/www/html/topico-03-wordpress`.

## Link do repositório GitHub

Adicionar aqui o link do repositório ou da pasta `topico-03/atividade-individual`.

## Próximos passos

No próximo tópico, devem ser considerados aspetos de segurança, como:

- Configurar HTTPS/SSL
- Rever permissões dos ficheiros
- Evitar exposição de credenciais
- Configurar backups
- Monitorizar logs
- Manter WordPress, temas e plugins atualizados
