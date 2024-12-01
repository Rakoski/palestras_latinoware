# Debian sid uma vida de aventuras - Paulo 

### Debian maintainer && software livre

## Softwares Livres

"qualquer software cuja licensa respeite essas 4 liberdades essenciais segundo a free software foundation"

- Uso 
- Entender e modificar
- Distribuir o original (copy left tem que ser com a mesma licensa, se vc quiser passar pra frente -> trabalho continuar livre sempre) 
- Distribuir o modificado


### open source
"código open source, segundo a open source initiative, é um código que respeite os 10 ite s da open software foundation"

### open source segundo debian
"software livre da debian, é um software que respeite os 10 princípios da free software timelapse"

## O Debian

### O projeto

Christian Stallman em 1983 -> todos os seus componentes fossem softwares livres 

- Fez de traz pra frente -> SO precisa de programas -> começou-se o Debian com editor de texto livre -> compilador livre

- SO -> GNU (O kernel é linux libre [versão modificada do linux que retira coisas do linxu que não são livres])

- O debian é um projeto que distribui o sistema GNU e um monte de componentes previamente arranjados pra ficar algo bem consistente e bacana

- Tem estatuto, contrato social, ideias, pensamentos, DFSG

- Pacote são instalados em linux (pode ter conjuntos de pacotes pra instalar um programa ou vários programas em 1 pacote só)

- "O meu Debian" -> o pacote distribui e coloquei esses arquivos no meu computador e disse pro meu <b>firmware</b> carregar esses arquivos pro meu sistema operacional -> DEBIAN STABLE (personal) 

### versões distribuidas

Reinstalar jamais - lema do cara kk

- Debian Stable (personal) (nesse momento é a 12) (bookworm) 
- antes da stable (old stable) 
- antes da antes da stable (old old stable)
- Estado de testes
- Sid (Instable)

### outras distribuições 

Uma versão mint ou ubuntu (fork do debian) NÃO É DEBIAN
Ubuntu 60% do que instalou está exatamente igual ao debian

## Debian Sid

- Unstable, development, rolling release
- Tudo que é novo no Debian chega aqui 
- Po podia ter isso no debian ne
- Manda um email e gera um request for package (intenção de empacotar) -> entra em contato com um Debian developer e um repositório público não pode só enviar e fodase
- Pronto aquele pacote está no debian se for aprovado
- Passa 5 dias e não apresenta problemas (após um teste QA rigorosíssimo)
- A partir de 2 anos, o Debian lança uma nova versão estável a partir do que está na SID

### Quem pode usar?

- Alguma experiência, desktop e uso não PROD
- Usufruir no que é bom no debian sid mas arcar com que acontece numa distro atualizada diariamente
- navegador chrome não abrir e não funcionar (vamo descobrir oqq deu muito bom pra aprender (script passou batido))

### Como não sofrer?

- Não pode ficar mt tempo sem atualizar pois muda mt
- tem que fazer downgrade se der merda e vc nn saber resolver 
- paciencia kk

### E se der zika?

alternativas de pacotes 

- apt
- dpkg
- chroot