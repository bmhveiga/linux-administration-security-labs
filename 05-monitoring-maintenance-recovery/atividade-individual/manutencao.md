
Manutenção
Objetivo

Definir verificações simples de manutenção para garantir que o serviço web continua funcional.

Serviço crítico

O serviço crítico é:

Nginx
Verificações de manutenção
Estado do serviço

Verificar se o Nginx está ativo:

systemctl is-active nginx
Arranque automático

Verificar se o Nginx inicia automaticamente no boot:

systemctl is-enabled nginx
Configuração

Validar a configuração antes de recarregar:

sudo nginx -t
Logs

Consultar logs em caso de erro:

sudo journalctl -u nginx -n 20 --no-pager
sudo tail -n 20 /var/log/nginx/error.log
Espaço em disco

Verificar espaço em disco:

df -h
Conclusão

A manutenção básica deve confirmar que o serviço está ativo, configurado para iniciar no boot, sem erros críticos e com espaço em disco disponível.
