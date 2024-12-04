# Como evitar troubleshooting em PROD?

- E o trabalho de um SRE

## BO EM PROD: WAR ROOM

- alerta: troubleshooting de performance
- BO maior ainda pode implicar na funcionalidade de algo que foi implementado incorretamente
- POST MORTEMS: relatórios pra não ter mais essa situação
- Realização de diagnósticos
- quanto + tempo leva, + caro fica

### Por quê evitar e como acontecem?

- BO não é só infra! Dev normalmente tbm é culpado
- BO pode ser da arquitetura, daí fudeu
- Perde-se tempo que poderia ter sido usado em features ou bugfixes já conhecidos

### Infra Idle e Over

- Idle -> Request do ambiente maior do que é necessário -> dinheiro jogado fora
- Over (muito pequeno) -> pode causar indisponibilidade e lentidão

## Como saber que um BO em PROD pode ocorrer?

- Entender a demanda -> planejamento, execução e análise

### Testes

- Testes de performance logo no início de uma nova aplicação
- pensamento em performance desde o início
- Evitar overengineering -> monitoramento e performance apenas o tanto quanto necessário
- testes de performance chegam de cima (gerência) no fodase
- ver os pilares que guiam os testes de performance
- entender a parte de infra, código e negócio -> tech lead / DEVOPS / SRE capaz 

### Monitoramento

- Métricas de performance em PROD
- SLOs -> Service Local Objectives -> Objetivo de quão boa a aplicação pode ficar 
- tempo de resposta configurável, não adiante colocar um tempo de 300ms se em testes todas as requests passam de 400ms
- tema do erro
- Experiência de usuário através de métricas objetivas (não funcional)

### Ferramentas de métricas

- Apache JMeter -> Workshop da Ariane Izac
- Prometheus com Grafana -> APIs e mais usados
- Flyway core monitoring -> exclusivo java
- precisamos entender o porquê dos testes não passarem, o sre precisa dar sugestões de melhorias

## Identificando integrações

### Como lidar com integrações que não lidam com performance?

- APIs externas podem não ter métricas ou configurações focadas em performance
- wae
- ambiente de testes pode escalar até o mínimo de prod pra simular PROD

### TPS

- quanto mais threads melhor performance (se bem feito)
- SLO -> SLI -> SLA
- Error budget (1% das requests apenas precisam ser acima de 300ms, por ex)