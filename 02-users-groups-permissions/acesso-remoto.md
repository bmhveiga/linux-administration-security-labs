# Acesso remoto por SSH

## Estado do serviço SSH

Foi verificado o estado do serviço SSH com o comando:

systemctl status ssh --no-pager

O objetivo deste comando é confirmar se o serviço SSH está instalado, ativo e disponível para aceitar ligações remotas.

A evidência foi guardada em:

evidencias/ssh-status.txt

## Endereço identificado

O endereço IP do servidor foi identificado com o comando:

hostname -I

A evidência foi guardada em:

evidencias/ip-servidor.txt

## Comando de ligação

Exemplo de comando utilizado para ligação SSH:

ssh bruno@192.168.89.128

Neste comando:

- ssh inicia a ligação remota segura.
- bruno é o utilizador Linux.
- 192.168.89.128 é o endereço IP do servidor Ubuntu.
- A porta padrão do SSH é a porta 22.

## Resultado obtido

O acesso remoto por SSH permite administrar o servidor Linux a partir de outro terminal, como o PowerShell no Windows, sem depender diretamente da consola da máquina virtual.

Com SSH é possível executar comandos remotamente, gerir ficheiros, verificar utilizadores e grupos, instalar pacotes, consultar logs e administrar o sistema com maior proximidade a um ambiente real de servidor.

## Limitações encontradas

O ambiente utilizado é uma VM local em modo NAT. Por isso, o acesso SSH funciona dentro do ambiente local, mas não representa ainda uma exposição pública como aconteceria numa VPS ou instância cloud.

Apesar disso, o teste é válido para aprendizagem porque simula a administração remota de um servidor Linux.

