# Wireshark: Desvendando o tráfego como um super herói da redes

### Christiane Borges Santos

Ethereal e wireshark - análise de protocolos de redes alguns falam que é sniffer

## Contextualização protocolos de redes

Como é o meio de transmissão?
- Regras padrões e especificações -> preparar a informação pra comunicação
- Um sistema é tão forte quanto sua conexão mais frágil e com falhas (humanas e técnicas)
- Um bom adm tem que diagnósticar o q ta acontecendo, segurança tem em conformidade com regulamentação?

## Wireshark

- Análise de protocólo, ou packet sniffer
- Dois modos: captura de pacotes e analisador de protocolos
- Sniffer captura 1 unidade de dados (PDU) de acordo com RFC (request for comic -> tudo que quiser saber sobre um protocolo vai la na RFC e consulta)

### Análises e estudo de caso

- Modo promiscuo da placa de rede tudo que tiver passando vc captura -> depende da possibilidade de habilitar esse parâmetro da placa de rede

### o que tem?

- Janela com sequencia
- Filtros
- menu comandos 
- janela análise de trafego

### Análise de trafego

exemplos: ip.addr == 200.17.56.16 (endereço ifg)

tcp e udp: protocolos que garantem a entrega

### caso de invasão

- Fez varredura de portas (era de uma impressora)
- Usaram a porta da impressora como forma de ataque
- Se a porta não ta sendo usada melhor fechada
- Filtrar por http: a mensagem de sucesso do navegador tem q aparecer
- ex: tcp.port == 80 e tc.port == 443

### Wireguard

- Protocolo de VPN open source
- Tecnologia de túnel p/ segurança
- Criptografa o tráfego

## Segurança e ética na análise de tráfego

- se o site nn usar http da pra pegar tudo pelo wireshark