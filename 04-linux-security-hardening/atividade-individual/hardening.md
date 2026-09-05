# Hardening Inicial

## Serviço analisado

O serviço publicado utiliza Nginx em Ubuntu Server.

## Medidas aplicadas ou verificadas

### 1. Firewall ativa

A firewall UFW está ativa e permite apenas as portas necessárias:

- 80/tcp
- 443/tcp
- 2222/tcp

### 2. SSH endurecido

A configuração efetiva do SSH mostra:

- porta SSH: 2222
- login root: desativado
- autenticação por chave pública: ativa
- autenticação por password: desativada

Isto reduz o risco de ataques por password e evita acesso direto como root.

### 3. HTTPS configurado

O Nginx foi configurado para redirecionar HTTP para HTTPS.

Foi usado um certificado self-signed para fins de laboratório.

Em produção, seria necessário usar um domínio e um certificado emitido por uma autoridade certificadora confiável.

### 4. Validação da configuração do Nginx

A configuração do Nginx foi validada com sucesso usando:

sudo nginx -t

### 5. Permissões da raiz web

A raiz web está em:

/var/www/html

Os ficheiros pertencem a `root:www-data`, com permissões de leitura para o serviço web.

## Riscos específicos

1. Certificado self-signed não é confiável para produção.
2. Porta 80 continua aberta, embora usada apenas para redirecionamento.
3. Qualquer ficheiro sensível colocado em /var/www/html poderia ficar exposto.
4. Configurações incorretas no Nginx podem quebrar o serviço.
5. Falta de monitorização contínua pode atrasar a deteção de problemas.

## Medidas que podem ser aplicadas agora

- Manter UFW ativo.
- Permitir apenas portas necessárias.
- Manter SSH sem login root.
- Manter password authentication desativada.
- Verificar permissões em /var/www/html.
- Validar Nginx antes de reload.

## Medidas para tópicos seguintes

- Usar certificado real com domínio e Let's Encrypt.
- Configurar monitorização contínua.
- Analisar logs regularmente.
- Configurar backups.
- Aplicar atualizações de segurança de forma rotineira.
- Implementar alertas para falhas de serviço.

## Conclusão

O serviço recebeu medidas iniciais de hardening suficientes para reduzir a superfície de ataque e validar que continua funcional depois das alterações.
