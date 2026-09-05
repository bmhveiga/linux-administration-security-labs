# Permissões aplicadas

## Ambiente utilizado

Ambiente utilizado: VM local com Ubuntu Server, executada no VMware Workstation Pro e acedida através do terminal/SSH.

## Utilizador e grupos

Comandos utilizados para identificação:

```bash
whoami
id
groups
```

Resumo:

- `whoami` identifica o utilizador atualmente autenticado.
- `id` mostra UID, GID, grupo primário e grupos suplementares.
- `groups` mostra os grupos aos quais o utilizador pertence.

O output foi guardado em:

```text
evidencias/identificacao-output.txt
```

No ambiente usado, o utilizador principal é `bruno`. O utilizador pertence a vários grupos, incluindo o grupo `sudo`, que permite executar tarefas administrativas com privilégios elevados quando necessário.

## Ficheiros criados

- `publico.txt`: ficheiro de teste com permissões mais abertas para leitura.
- `restrito.txt`: ficheiro de teste com acesso mais limitado.
- `script.sh`: ficheiro de script usado para testar permissão de execução.

## Permissões aplicadas

| Ficheiro | Permissão | Justificação |
|---|---:|---|
| publico.txt | 644 | Permite que o dono leia e escreva, enquanto grupo e outros apenas leem. É adequado para ficheiros públicos ou informativos. |
| restrito.txt | 640 | Permite leitura e escrita ao dono, leitura ao grupo e nenhum acesso a outros. É mais adequado para ficheiros com informação restrita. |
| script.sh | u+x | Adiciona permissão de execução apenas ao dono, permitindo testar o script sem dar execução a todos os utilizadores. |

## Relação com o princípio do menor privilégio

O princípio do menor privilégio recomenda conceder apenas as permissões necessárias para cada utilizador, grupo ou serviço realizar a sua função.

As permissões aplicadas são mais adequadas do que permissões totais para todos porque limitam o acesso:

- `publico.txt` pode ser lido por todos, mas só alterado pelo dono.
- `restrito.txt` impede acesso de outros utilizadores fora do dono e do grupo.
- `script.sh` recebe execução apenas para o dono, evitando execução desnecessária por outros utilizadores.

Em vez de usar permissões excessivas como `777`, foram aplicadas permissões específicas conforme o objetivo de cada ficheiro. Isto reduz riscos de alteração indevida, execução não autorizada e exposição de informação.
