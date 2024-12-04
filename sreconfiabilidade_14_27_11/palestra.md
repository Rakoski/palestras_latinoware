# SRE: Aplicações escaláveis e confiáveis

- Como ir adicionando novas feats sem perder a confiabilidade?

## Métricas de performance

- Demand driven performance -> planejamento de capacidade

### SLI - Service Level Indicator

- Quanto é bom meu software?
- Setado pela gestão e SREs e devops

### SLA - Service Level Alignment

- Contrato legal que caso quebrado vai ter consequências
- Jurídico, licensas, etc

### SLO - Service Level Objectives

- Até aonde posso chegar (em performance e confiabilidade) com meu time?
- Metas de objetivos de confiabilidade, escalabilidade e experiência do usuário
- Setado pelo SRE, devs e devops, além da gestão conferir

## Mensurando a confiabilidade

### De 2.500.000 requests

- 2.497.000 foram 200 OK

- SLI -> % com retorno 200 OK (requests top)
- SLO -> Agora queremos 99,9% das requests com sucesso diariamente
- Error budget -> 0.1% das requests possuem errors
- Capacity planning

### Datadog

- Nós mostra o quão bem nossa aplicação está indo
- Até onde podemos chegar