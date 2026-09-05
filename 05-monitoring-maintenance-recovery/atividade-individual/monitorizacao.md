# Monitorização

## Objetivo

Verificar o estado básico do sistema e do serviço web publicado.

## Verificações realizadas

### Tempo de atividade

Foi usado `uptime` para verificar há quanto tempo o servidor está ligado e a carga média do sistema.

### Memória

Foi usado `free -h` para verificar o consumo de memória.

### Espaço em disco

Foi usado `df -h` para verificar a utilização do disco.

### Estado do serviço web

Foi usado `systemctl status nginx` para confirmar se o Nginx está ativo.

### Portas em escuta

Foi usado `ss -tulpn` para confirmar as portas relevantes:

- 80/tcp para HTTP;
- 443/tcp para HTTPS;
- 2222/tcp para SSH.

## Resultado

O sistema estava operacional, o serviço Nginx estava ativo e as portas necessárias estavam em escuta.

## Evidência

A evidência está em:

`evidencias/topico-05-monitorizacao-logs.txt`
