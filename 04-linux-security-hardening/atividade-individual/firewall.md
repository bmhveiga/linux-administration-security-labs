# Firewall

## Ferramenta usada

A firewall utilizada foi UFW.

## Estado da firewall

A firewall está ativa.

## Regras permitidas

Foram permitidas apenas as portas necessárias:

- 80/tcp para HTTP.
- 443/tcp para HTTPS.
- 2222/tcp para SSH.

## Justificação das portas

### Porta 80/tcp

Usada para HTTP. Nesta configuração, a porta 80 redireciona o tráfego para HTTPS.

### Porta 443/tcp

Usada para HTTPS. É a porta principal para acesso web encriptado.

### Porta 2222/tcp

Usada para SSH. A porta padrão 22 foi substituída por 2222 para reduzir exposição e ruído de tentativas automáticas.

## Validação

A evidência mostra que UFW está ativo e permite apenas as portas necessárias.

Ficheiro de evidência:

evidencias/topico-04-validacao-seguranca.txt

## Cuidado importante

Em servidores remotos, a firewall não deve ser ativada sem confirmar primeiro que a porta SSH está permitida. Caso contrário, o administrador pode perder acesso ao servidor.
