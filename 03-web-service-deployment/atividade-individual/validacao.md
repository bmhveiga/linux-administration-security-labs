# Validação WordPress

## URL testado

http://<VPS_PUBLIC_IP>/topico-03-wordpress/

Painel administrativo:

http://<VPS_PUBLIC_IP>/topico-03-wordpress/wp-admin/

## Resultado obtido

A instalação WordPress foi concluída com sucesso. O painel administrativo ficou acessível pelo navegador, confirmando que Apache, PHP, MariaDB e WordPress estão a funcionar em conjunto.

## Evidência

- `evidencias/apache-validado.txt`
- `evidencias/php-validado.txt`
- `evidencias/mariadb-validado.txt`
- `evidencias/base-dados-wordpress.txt`
- `evidencias/ficheiros-wordpress.txt`
- `evidencias/permissoes-wordpress.txt`
- `evidencias/validacao-wordpress-final.txt`
- Print do painel WordPress no navegador, com IP e dados sensíveis ocultados antes de publicação.

## Relação entre WordPress, servidor web, PHP e base de dados

O Apache recebe os pedidos HTTP e serve a aplicação WordPress. O PHP executa os ficheiros dinâmicos do WordPress. O MariaDB armazena os dados da aplicação, como configurações, utilizadores, páginas e conteúdos. O WordPress utiliza estes componentes em conjunto para gerar a página apresentada ao utilizador.

## Cuidados de segurança a considerar no próximo tópico

- Configurar HTTPS/SSL.
- Evitar expor credenciais em prints, ficheiros ou repositórios.
- Manter WordPress, temas e plugins atualizados.
- Rever permissões dos ficheiros.
- Restringir acessos administrativos.
- Configurar backups.
- Monitorizar logs do Apache e do sistema.
