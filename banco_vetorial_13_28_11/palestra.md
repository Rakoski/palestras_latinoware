# Banco de dados vetorial com inteligência artificial

Não amarra os vetores - garantia de controle das informações

- https://weaviate.io
- github dudanogueira e https://github.com/weaviate
- slack deles
- workshops online
- https://weaviate.io/papers - review de papers
- podcast
- knowledgecards
- recipes
- verba
- https://console.weaviate.cloud - instância gratuita em nossa cloud pra testar e experimentar
- modo embutido pip install weaviate-client
- client = weaviate.connect_to_embedded()
- pra prod: helm pra kubernetes


## Busca

- principal coisa que o banco vetorial faz é busca
- SQL com like e WHERE nn é busca, é filtro
- como fazer buscas da melhor forma?
- Tem matemática

### Tipos:

- Semântica 
- palavra chave
- Híbrida

## Inserindo objetos no bd vetorial

<code>
collections = client.collections.create(</br>
    "Animais",</br>
    vectorizer_config=wvc.config.Configure.Vectorizer.text2vec_cohere()</br>
)
</br>
collections.data.insert_many([</br>
    {"text": "cachorros são fofos"}, // 1 objeto</br>
    {"text": "gatos são fofos, mas estranhos"}, // 2 objeto</br>
    //etc..</br>
])
</code>
<br>

# Buscas 

- vector embedding: um frase, um texto que será buscada

## Semântica / vetorial

<code>
for obj in collection.query.near_text(
    "animais domésticos",
    return_metadata=wvc.query.
)
</code>

- da pra buscar por qualquer idioma que o modelo suportar

### query

- query: domestic

- distância: 0.674535435435
{text: "cachorros são fofos"} // objeto mais próximo da query

### retrieval augmented generation

- daria pra fazer um banco SQL pros dados do user e um pra buscas, por exemplo colocar todos os cursos nesse banco doido e o resto inserts e updates no sql

## keyword search 

### Okapi_BM25

- método que chama e faz a busca por palavra chave
- indexa os tokens e faz uma busca pra você

<code>
query = collection.query.bm25(<br>
    "animais da floresta são fofo",<br>
    return_metadata=wvc.query.MetadataQuery(score=True, explain_score=True),<br>
)<br>


for obj in query.objects:<br>
    print(f"\n score: {obj.metadata.score}")
</code></code>

## Hybrid search

<code>
query = collection.query.hybrid(<br>
    "animais da floresta são fofo",<br>
    return_metadata=wvc.query.MetadataQuery(score=True, explain_score=True),<br>
)
</code><br>-

# Vetores e suas dimensões

- pra exemplificar vamos colocar que o vetor é 1 dimensão

## RGB 

- maneira através de números pra colocar em números
- representa um sentido em números 

### calculando distâncias entre vetores

- Manhattan, squared euclidian, etc

# Os desadios de calcular distâncias entre vetores

- muito tempo se forem objetos muito grandes

## HNSW: hierarquical navigable small world

- Indo de camada em camada pra encontrar os objetos, tanto testo como imagens

- pegamos nossa imagem, dividimos em quadrados, vetorizamos os quadrados, qual desses quadrafos está mais próximo da imagem que eu tenho?

- Multimodal niver hard: fazer a busca com modelo da meta chamado bind que busca miau e acha um gato, ou coloca a imagem de um gato e encontra um audio falando miau

## Rag 

- Hybrid search 
- pega os objetos mais relevantes pro que queremos
- joga pra llm
- consigo responder a pergunta com contexto semântico próximo
- LLM gera uma resposta em linguagem natural

### 
- torna objetos de uma query em chunks


### 
- antes de pesquisar na llm (caro), tem que ver no banco se a pergunta já foi pesquisada
- faz uma pesquisa na llm grande
- da pra ver uma pergunta e indicar a palestra que responde ela

## Self-healing db

- Acerta datas (se alguém colocar data 98/10/12 e era pra ser 12/10/98 auto conserta antes de colocar)
- acerta números e strings

### named vectors

- mais de um vetor por objeto
- pode buscar por exemplo pelo texto e pela imagem ou comparar resultados usando diferentes modelos

### multi tenant
- isola os dados de um tenant e evita pesquisas entre os tenants, isola os dados garantidamente
- hnsw fica na memória (1 milhao de obj fica tudo na memória)
- clientes que não usam -> tira da memória
- 30, 40 clientes na memória do hsnw e o resto nn usa

### compressão

- não é tão próximo mas da pra encontrar

### algoritmo de consenso RAFT

- pra multiplos clusters

### repares assíncronos

- man me fala oq eu perdi

### estratégia de busca acorn

- 10x de performance em alguns tipos de buscas
- ACORN: Permormant and Predicate-Agnostic Search over vector embeddings and structured data

## como ganham dinheiros?

- weavite cloud services
