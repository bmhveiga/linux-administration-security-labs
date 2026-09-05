# Tópico 04 - Atividade Prática Individual

## Tema

Segurança inicial e hardening de um serviço web publicado em Linux.

## Objetivo

Esta atividade aplica medidas iniciais de segurança ao serviço publicado no Tópico 03.

O foco foi:

- identificar serviços e portas;
- compreender a superfície de ataque;
- verificar e documentar regras de firewall;
- propor medidas iniciais de hardening;
- validar que o serviço web continua acessível;
- publicar evidências seguras no GitHub.

## Serviço analisado

O serviço web utilizado nesta atividade é um site HTML simples publicado com Nginx em Ubuntu Server.

## Estrutura

- `superficie-ataque.md`: identificação de serviços, portas e riscos.
- `firewall.md`: estado e regras da firewall.
- `hardening.md`: medidas iniciais de hardening propostas/aplicadas.
- `validacao.md`: validação do serviço após alterações.
- `comandos.txt`: comandos utilizados.
- `evidencias/`: outputs seguros recolhidos no servidor.

## Evidência principal

A evidência principal está em:

`evidencias/topico-04-validacao-seguranca.txt`

## Observação de segurança

Foram evitadas credenciais, chaves privadas e dados sensíveis na documentação pública.
