# Superfície de Ataque

## Serviço web usado

O serviço web publicado no Tópico 03 utiliza Nginx num servidor Ubuntu.

A raiz do conteúdo web está em:

/var/www/html

## Serviços relevantes

Foram observados os seguintes serviços principais:

- Nginx: serviço web.
- SSH: acesso remoto ao servidor.
- UFW: firewall local do servidor.

## Portas observadas

As portas em escuta relevantes são:

- 80/tcp: HTTP.
- 443/tcp: HTTPS.
- 2222/tcp: SSH configurado numa porta personalizada.

## Portas necessárias

- 80/tcp é necessário para receber pedidos HTTP e redirecionar para HTTPS.
- 443/tcp é necessário para servir o site por HTTPS.
- 2222/tcp é necessário para administração remota por SSH.

## Portas não necessárias

Qualquer porta que não esteja associada ao serviço web ou à administração remota deve permanecer bloqueada.

## Riscos iniciais identificados

1. Exposição desnecessária de portas.
   - Quanto mais portas abertas, maior a superfície de ataque.

2. Acesso SSH inseguro.
   - Login direto como root ou autenticação por password aumentam o risco.

3. Tráfego HTTP sem encriptação.
   - Dados transmitidos por HTTP podem ser observados na rede.

4. Permissões incorretas na raiz web.
   - Permissões muito abertas podem permitir alterações indevidas.

5. Certificado self-signed.
   - Serve para laboratório, mas o navegador não confia nele em produção.

## Conclusão

A superfície de ataque inicial foi reduzida ao manter apenas as portas necessárias para o serviço web e para administração remota.
