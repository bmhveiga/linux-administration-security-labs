
Continuidade Operacional
Objetivo

Definir um plano simples de continuidade operacional para o serviço web publicado.

Serviço crítico

O serviço crítico é:

Nginx

Este serviço é responsável por entregar a página web aos utilizadores.

Ficheiros e configurações críticas

Os principais itens críticos são:

/var/www/html: conteúdo web publicado;
/etc/nginx/sites-available/default: configuração do site Nginx;
/etc/nginx/nginx.conf: configuração global do Nginx;
/var/log/nginx/: logs de acesso e erro.
Logs importantes

Logs úteis para diagnóstico:

/var/log/nginx/access.log
/var/log/nginx/error.log
journalctl -u nginx
Periodicidade de backup

Para este laboratório, o backup foi feito manualmente.

Num ambiente real, uma periodicidade recomendada seria:

backup diário para conteúdo web;
backup antes de alterações de configuração;
backup antes de atualizações importantes;
retenção de várias versões recentes.
Procedimento de recuperação

Procedimento simples:

Confirmar que o serviço está com problema.
Verificar logs do Nginx.
Restaurar backup numa pasta de teste.
Validar os ficheiros restaurados.
Substituir os ficheiros afetados, se necessário.
Validar configuração com nginx -t.
Recarregar Nginx com systemctl reload nginx.
Testar o site com curl.
Critérios de validação após recuperação

Após uma recuperação, validar:

Nginx ativo;
configuração Nginx válida;
portas necessárias em escuta;
site responde por HTTP/HTTPS;
logs sem erros críticos;
conteúdo web recuperado.
Medidas adicionais recomendadas

Para um ambiente mais avançado:

automatizar backups;
guardar backups fora do servidor;
usar certificados confiáveis em produção;
monitorizar logs regularmente;
criar alertas para falhas do serviço;
testar recuperação periodicamente.
Conclusão

A continuidade operacional depende de monitorização, logs, backup e validação. O serviço deve ser recuperável, não apenas publicado.
