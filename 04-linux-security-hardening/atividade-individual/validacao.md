# Validação

## Objetivo

Validar que o serviço web continua funcional depois das medidas iniciais de segurança.

## Validações realizadas

### Serviço Nginx

Foi verificado que o serviço Nginx está ativo e em execução.

### Portas em escuta

Foram verificadas as portas:

- 80/tcp
- 443/tcp
- 2222/tcp

### Firewall

Foi verificado que UFW está ativo e permite apenas as portas necessárias.

### Configuração Nginx

A configuração foi validada com:

sudo nginx -t

Resultado esperado:

- syntax is ok
- test is successful

### HTTP

Foi validado que HTTP responde com redirecionamento:

HTTP/1.1 301 Moved Permanently

Isto confirma que a porta 80 redireciona para HTTPS.

### HTTPS

Foi validado que HTTPS responde com sucesso:

HTTP/1.1 200 OK

Como o certificado é self-signed, foi usado `curl -k` para ignorar o aviso de confiança do certificado durante o teste.

### SSH

Foi validado que SSH usa:

- porta 2222
- PermitRootLogin no
- PubkeyAuthentication yes
- PasswordAuthentication no

## Evidência

A evidência completa está em:

evidencias/topico-04-validacao-seguranca.txt

## Conclusão

O serviço continuou acessível após as alterações de segurança. A firewall está ativa, o Nginx está funcional, HTTP redireciona para HTTPS e SSH está configurado com medidas de hardening.
