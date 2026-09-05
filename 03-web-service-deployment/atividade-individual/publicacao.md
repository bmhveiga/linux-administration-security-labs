
## Pasta de publicação

A aplicação WordPress foi publicada em:

/var/www/html/topico-03-wordpress

## URL de acesso

http://<VPS_PUBLIC_IP>/topico-03-wordpress/

Painel administrativo:

http://<VPS_PUBLIC_IP>/topico-03-wordpress/wp-admin/

## Estado da instalação

A instalação foi concluída com sucesso. O painel administrativo do WordPress ficou acessível no navegador.

## Comandos principais utilizados

Os comandos principais foram registados no ficheiro `comandos.txt`.

## Limitações encontradas

Durante a preparação, foi identificado que o Nginx estava ativo na porta 80. Como a rota escolhida foi WordPress com Apache, o Nginx foi parado e desativado para libertar a porta 80.

A configuração HTTPS/SSL não foi realizada nesta atividade, pois o foco principal do tópico foi a publicação do serviço web. A segurança, hardening, logs, monitorização e backups serão aprofundados nos tópicos seguintes.
