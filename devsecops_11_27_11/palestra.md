# DevSecOps - as melhores práticas de um pipeline seguro

## DevSecOps

- Processo Fluído de infra e dev
- Agora o povo de infra da empresa dele participa do planejamento dos novos sistemas
- Dev apresenta as tecnologias p/ time de rede, infra e banco
- Será que é bom essa tec pra esse tipo de servidor?

### Ex: bastante disco e ram limitada

- SQLite ou PostgreSQL: operações queue mt boas
- Evitar Redis e caches de memória
- Evitar a JVM (java ou kotlin, por ex) pois usa muita memória.
- Node ou Php funcionariam muito bem

## Como foi implementado?

### Antes

- Junta uma semanade mudanças nos códigos dos times, por exemplo
- Faz a release tudo junto
- Caso quebre algo, problemão -> pouco fluído e ágil

### Depois

- Após um time de devsecops: entregas menores mas persitentes
- Caso quebre algo: time de dev arruma e já faz a correção
- Feature flags

## Cultura devops

-   --> plan -> code -> build -> test -> | DEV<br>
  | monitor <- deploy <- release <--      OPS
- Integração de ambientes e pessoas
- Entregas rápidas
- Pessoas e processos

## Definindo o escopo

- Como devops não batem a cabeça com escopo mal definido?

### Segurança desde o planejamento

- Quais os problemas da linguagem?
- Quais as boas práticas de desenvolvimento seguro para a linguagem/framework? Ex: refresh tokens com nextauth | spring security e dofilters pra sprign boot
- Codigo determina infra & build logo no planejamento do escopo -> ex: microserviços ou monolito? Vai ser escalável depois se por enquanto for monolito?
- testes de: Aceitação, integração e segurança
- caso: não podem fazer engenharia reversa pra descobrirem endpoints e rotas, por ex
- Load balancing, cluster de kubernetes será deployado como?
- Se a app for interna -> VPN, como pessoal irá se conectar?

### Plan

- confiabilidade, integridade e disponibilidade
- zero access: nenhum acesso até a pessoa precisar 
- acesso escalável (chmod por ex) -> primeiro read, depois write e dps admin apenas em último caso

### Code

- Testes unitários na Pipe CI/CD em PROD
- Garantir branches main e dev estejam na mesma linha -> EVITAR MERGEBACKS
- Ambiente -> quem fez o que em qual branch? Github actions, azure devops

### Build 

- Análise estática de código -> essa função tem um parâmetro que pode ser mais restritivo. ex de SAST: sonarlint 
- code coverage 
- SLA: Segurança de licensas e complience

### Test

- DAST: faz acessos de forma automatizada
- Tech lead precisa ter carta branca pra impementar esse tipo de coisa, mesmo que custe tempo

### Release

- Testes de aceitação dos stakeholders: é a feature que foi desejada?
- Pentests, eng reversa, força bruta -> antes de subir

### Deploy 

- CI/CD sem conexão com máquina local
- testes no server com ambiente do server
- cluster kubernetes configurado


