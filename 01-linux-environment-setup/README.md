# Atividade Prática 1 — Preparação do ambiente Linux

## 1. Objetivo

Esta atividade tem como objetivo preparar o ambiente Linux utilizado no módulo **Linux e Segurança na Cloud**, criar uma estrutura inicial de projeto, executar comandos básicos de identificação do sistema e organizar as primeiras evidências técnicas.

A atividade também serve como ponto de partida para transformar a aprendizagem prática em documentação técnica no GitHub, criando um registo visível do processo de configuração, diagnóstico e evolução do laboratório.

## 2. Ambiente utilizado

O ambiente escolhido para esta primeira fase foi uma **máquina virtual local** com Ubuntu Server.

### Configuração principal

* Sistema operativo host: Windows
* Hypervisor: VMware Workstation Pro
* Tipo de hypervisor: Tipo 2 / Hosted
* Máquina virtual: Ubuntu Server 24.04 LTS
* Utilizador Linux: bruno
* Nome do servidor: ubuntuserver
* Endereço IP da VM: 192.168.89.128
* Modo de rede: NAT
* Acesso remoto: SSH através do PowerShell
* Repositório remoto: GitHub

## 3. Trilho seguido

O trilho seguido foi **VM local**.

Esta escolha foi feita porque permite praticar Linux num ambiente isolado, controlado e sem custos adicionais. A VM local permite repetir comandos, errar, corrigir, testar configurações e documentar o processo sem afetar o computador principal.

A máquina virtual funciona como um mini-laboratório de servidor Linux, simulando várias práticas que também podem ser aplicadas futuramente a uma VPS ou a uma instância cloud.

## 4. Comparação com outros ambientes considerados

Durante a preparação do módulo, foram considerados outros caminhos possíveis para praticar Linux em contexto de servidor e cloud.

### VM local

A VM local é executada dentro do próprio computador, usando um hypervisor como VMware Workstation Pro ou VirtualBox.

**Vantagens:**

* Sem custo adicional.
* Ambiente seguro e isolado.
* Ideal para aprendizagem inicial.
* Permite testar comandos sem expor o servidor à internet.
* Boa base antes de avançar para VPS ou cloud.

**Limitações:**

* Não possui IP público.
* Não representa totalmente um ambiente remoto real.
* Depende dos recursos do computador local.

### VPS tradicional

Uma VPS é um servidor virtual remoto alugado a um fornecedor externo, como Hostinger, DigitalOcean, Hetzner, AlexHost ou outro provedor.

**Vantagens:**

* Mais próximo de um servidor real.
* Acesso remoto por SSH através da internet.
* Possui IP público.
* Boa opção para praticar serviços web, firewall, SSH e administração remota.

**Limitações:**

* Tem custo mensal.
* Exige mais cuidado com segurança.
* Pode gerar custos se ficar ativa durante muito tempo sem necessidade.

### AWS Free Tier

A AWS Free Tier permite experimentar serviços cloud com limites gratuitos ou créditos iniciais, dependendo das condições da conta.

**Vantagens:**

* Boa entrada no mundo cloud.
* Permite contacto com conceitos reais de cloud computing.
* Útil para aprender EC2, segurança, rede, billing e monitorização.
* Relevante para uma futura trajetória em cloud support, sysadmin ou DevOps.

**Limitações:**

* Mais complexa para iniciantes.
* Exige atenção ao billing.
* Serviços esquecidos ou limites ultrapassados podem gerar custos.
* Requer disciplina para criar alertas, controlar recursos e eliminar o que não estiver em uso.

## 5. Decisão atual

Para esta primeira fase, a decisão foi começar com **VM local**, porque é a opção mais segura, económica e adequada para construir a base prática em Linux.

A estratégia de aprendizagem será gradual:

```text
VM local
→ SSH e documentação no GitHub
→ VPS simples ou AWS Free Tier
→ Cloud, segurança, monitorização e automação
```

Assim, a VM local constrói a base. Depois, uma VPS ou AWS Free Tier poderá ser usada como próxima fase para aproximar a prática de um ambiente remoto real.

## 6. Estrutura inicial do projeto

A estrutura criada para a atividade é:

```text
Linux-e-Seguranca-na-Cloud/
├── inicio-e1/
│   ├── evidencias/
│   ├── comandos-registo-01.txt
│   └── README.md
└── produto-final/
```

## 7. Descrição das pastas e ficheiros

### inicio-e1/

Pasta destinada à primeira atividade prática do módulo.

### inicio-e1/evidencias/

Pasta reservada para guardar prints, capturas de ecrã e outros comprovativos técnicos.

### inicio-e1/comandos-registo-01.txt

Ficheiro usado para registar os comandos executados e explicar a finalidade de cada um.

### inicio-e1/README.md

Documento técnico inicial com a descrição do ambiente, trilho seguido, estrutura criada, observações e decisões técnicas.

### produto-final/

Pasta reservada para organização futura das evidências finais do módulo.

## 8. Comandos iniciais utilizados

Alguns dos comandos utilizados nesta fase foram:

```bash
whoami
pwd
hostname
hostname -I
ip a
ping -c 4 8.8.8.8
ping -c 4 google.com
sudo apt update
sudo apt upgrade -y
sudo apt install git tree -y
git --version
tree --version
ssh-keygen -t ed25519 -C "brunomhv@gmail.com"
ssh -T git@github.com
git clone git@github.com:bmhveiga/Linux-e-Seguranca-na-Cloud.git
tree
git status
```

## 9. Integração com GitHub

O projeto foi integrado com GitHub através de uma chave SSH criada dentro do Ubuntu Server.

O fluxo utilizado foi:

```text
Ubuntu Server VM
→ criação da chave SSH
→ adição da chave pública ao GitHub
→ teste de autenticação SSH
→ clone do repositório
→ criação da estrutura do projeto
→ commit
→ push para o GitHub
```

Este processo permite que a documentação criada dentro do ambiente Linux seja enviada para o repositório remoto, transformando a atividade num projeto técnico versionado.

## 10. Problema encontrado e resolução

Durante a preparação do ambiente, foi identificado um problema de conectividade.

A VM conseguia ser acedida por SSH a partir do Windows, mas inicialmente não conseguia aceder à internet. O comando `apt update` falhava com erros de resolução de nomes e os testes de conectividade indicavam falha no acesso externo.

Foram realizados testes com:

```bash
ping -c 4 8.8.8.8
ping -c 4 google.com
```

Após verificar a configuração de rede da VM no VMware, confirmou-se que o modo NAT estava selecionado. O problema foi identificado no Windows: o serviço **VMware NAT Service** estava parado.

Depois de iniciar o serviço VMware NAT Service, a VM passou a conseguir aceder à internet normalmente.

Este problema mostrou que:

* SSH local não garante acesso à internet.
* O modo NAT depende dos serviços de rede do VMware.
* Diagnosticar rede faz parte da administração de sistemas.
* Testes como `ping`, `ip a`, `hostname -I` e verificação de serviços ajudam a encontrar a causa raiz.

## 11. Observações finais

Esta primeira fase permitiu preparar o ambiente base para o módulo, instalar ferramentas essenciais, testar conectividade, configurar Git, integrar o Ubuntu Server com GitHub e criar a estrutura inicial da atividade.

A próxima fase poderá explorar uma VPS simples ou AWS Free Tier, mas com atenção especial a custos, segurança, billing, controlo de recursos e boas práticas de administração.
