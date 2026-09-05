# Logs

## Objetivo

Consultar logs recentes do sistema e do serviço web para identificar eventos relevantes.

## Logs consultados

Foram consultados:

- logs do serviço Nginx via `journalctl`;
- logs de erro do Nginx em `/var/log/nginx/error.log`.

## Comandos usados

```bash
sudo journalctl -u nginx -n 20 --no-pager
sudo tail -n 20 /var/log/nginx/error.log
Evento relevante identificado

Nos logs do Nginx foi possível observar eventos de ciclo de vida do serviço, como arranque, paragem e reload.

Exemplo de evento relevante:

Reloaded nginx.service

Este evento indica que o serviço Nginx recarregou a configuração sem necessidade de parar completamente o serviço.

Interpretação

Os logs são importantes porque funcionam como fonte de verdade para diagnóstico técnico. Eles permitem confirmar se um serviço iniciou, parou, falhou ou recarregou corretamente.

Evidência

A evidência está em:

evidencias/topico-05-monitorizacao-logs.txt
