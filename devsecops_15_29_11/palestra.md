# DevSecOps - The vulnerabilities in your application might not be in your code

## devops vs devsecops

- plan -> code -> build -> test -> release -> deploy -> monitor -> plan

### tipos comuns de vulnerabilidades

- source code
- componentes sistema
- confiança
- credenciamento
- falta de encriptação
- ameaça de dentro
- vulnerabilidade psicológica
- autenticação inadequada
- falhas de injection
- exposição de dados sensiveis
- falta de monitoramento e logs
- vulnerabilidade de shared tenancy (nao sei o que é)

###

- zero trust
- logar tudo que acontece no ambiente em prod

## suply chain security

- coisas de terceiros (dependencias)
- onde geralmente temos terceiros:

### package & deploy 

- SBOMs
- assinatura e provanância de código
- artifato do repositório

### build

- ci/cd
- containers e registradores
- dependencias

### code

- acesso as IDEs
- review de código fonte (sonarlint por ex)
- Source code management (SCM)

## SBOMs

- lista de receitas de tudo que foi usado pra fazer a aplicação
- nome do autor, componente do código fonte
- dependencias, bibliotecas
- nome do cara q desenvolveu os bgl

### Software Component Analysis - SCA

- passa em todo código que eu desenvolvi
- SCA -> notificar todos os times que dependem da minha aplicação uma vulnerabilidade possível
- notificar compliency e das licensas de códigos em terceiros usados (licensas gptl e apache são incompativeis, por ex)

### oq passa na pipe pra subir?

- depedency track 
- dependency check -> fica traqueando o pacote xpto ta vulnerável agora, por exemplo
- se minha app faz deploy a cada 6 meses, se eu lancei a minha versão hj e eu só vou lançar outra em março e a vuln.<br> sai no dia 1 de dez. eu só vou corrigir ela na próxima, daí fudeu 

## Como começar DevSecOps na empresa?

- SAST e SCA
- component: nome da biblioteca, dependencia
- version: olha essa versão quebra comp com tal e tal e tal coisa (major change no meu código p poder garantir que eu tenha isso)
- group: grupo do bgl se é vulnerável ou nao de acordo com o resto do codigo
- licensa (auto explicativo)
- vulnerabilities: quantas foram encontradas e se ta grave ou nn

### e se o dev não corrigir na máquina?

- deu a ferramente pra ele ver que ta errado a dependencia na maquina dele?
- bloqueia na pipe
