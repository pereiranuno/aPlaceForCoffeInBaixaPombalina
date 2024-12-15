# API Geometry Search - Processamento de Pontos de Interesse

Este repositório contém um **notebook Python** que interage com uma API de pesquisa geográfica para obter, processar e visualizar pontos de interesse (POIs) com base em categorias específicas. A aplicação principal é realizar a análise de dados geográficos e filtrá-los conforme critérios definidos. Foi feito um validação destra informação com outra fonte nesse caso utilizando o motor de busca da Google Através de tecnica Web Scrapping.

---

## Funcionalidades



- **Integração com a API Category Search:**
  - Envia requisições à API para obter categorias de ponto de interesse, baseado em definição de keywords de inclusão/exclusão.
- **Integração com a API Geometry Search:**
  - Envia requisições à API para obter POIs com base em categorias e geometrias definidas.
- **Processamento dos Resultados:**
  - Extração de informações relevantes, como nomes, endereços, categorias e coordenadas.~
- **Validação da qualidade dos dados recebidos:**
  - Validação da qualidade da informação recebida e validação do conteudo com fonte suplmentar, nesse caso motor de busca Google atrabés de Web Scrapping.
- **Exportação de Resultados:**
  - Os resultados são organizados em um `DataFrame` e salvos num ficheiro CSV para posterior análise.
- **Visualização Geográfica:**
  - Representação dos POIs num mapa interativo utilizando a biblioteca **Folium**.

---

## Estrutura do Repositório

- **`main.ipynb`**: Ficheiro principal contendo o código completo do projeto.
- **`data/categories_id.csv`**: Ficheiro de saída com os IDs das categorias processadas e filtradas.
- **`data/input_coordinates.csv`**: Ficheiro com dados de latitude e longitude dos vertices do pligono que define a Baixa Pombalina.
- **`data/keywords.csv`**: Ficheiro com palavras-chave utilizadas como critério para inclui/excluir as categorias recebidas da APi tomtom.
- **`logs/*`**: Pasta com os logs de todas as comunicações efetudas via APIs e pedidos Http via Web Scrapping.~
- **`resulted_poi_api_tomtom.csv`**: Ficheiro csv com o conteudo recebido via API tomtom
- **`validated_poi_googlesearchcsv`**: Ficheiro csv com o conteudo validado via Web Scrapping via Motor de Busca Google
- **`README.md`**: Este ficheiro, que documenta o projeto.
- **Outros ficheiros auxiliares**:
  - Ficheiros HTML ou JSON gerados para visualização de dados (se aplicável).

---


## Tecnologias Utilizadas

- **Python 3.x**
- **Bibliotecas**:
  - `requests`: Para realizar requisições HTTP, como chamadas a APIs e obtenção de conteúdo web.
  - `pandas`: Para manipulação e análise de dados, especialmente em estruturas tabulares como DataFrames.
  - `json`: Para manipular dados no formato JSON.
  - `csv`: Para manipular ficheiros CSV, permitindo leitura e escrita de dados tabulares.
  - `folium`: Para criar mapas interativos e visualizar dados geográficos.
  - `IPython.display.display`: Para exibir elementos interativos, como mapas e tabelas, em notebooks.
  - `uuid`: Para gerar identificadores únicos (UUIDs) em dados ou operações.
  - `seaborn`: Para criar gráficos estatísticos estilizados de forma simples.
  - `bs4 (BeautifulSoup)`: Para extrair e analisar dados de ficheiros HTML e XML, ideal para web scraping.
  - `base64`: Para codificar e decodificar dados no formato Base64, comum em algumas respostas de APIs.



---

## Como Utilizar

### 1. Instalar Dependências
Certifica-te de que tens o Python e as bibliotecas necessárias instaladas. Podes instalar as dependências através do `pip`:
```bash
pip install requests pandas folium
```

### 2. Executar o Notebook
Abre o ficheiro main.ipynb no Jupyter Notebook ou Google Colab.
Atualiza os seguintes parâmetros no código:
API_KEY: Inserir a chave de acesso à API.
url e params: Define os parâmetros necessários para a API Geometry Search.
keywords e exclude_keywords: Define as palavras-chave de inclusão e exclusão para o filtro de categorias.
Corre todas as células do notebook para executar o processamento e gerar os ficheiros de saída.~
ZETY_API_KEY: Inserir a chave de acesso à API, caso não tenha conta, deverá criar uma através de: https://app.zyte.com/

### 3. Resultado
O resultado principal será salvo em data/validated_poi_googlesearch.csv, contendo informações sobre os pontos de interesse cumprindo os requisitos definidos. 
Se a visualização geográfica estiver ativa, o mapa será gerado no notebook e pode ser exportado para um ficheiro HTML.
