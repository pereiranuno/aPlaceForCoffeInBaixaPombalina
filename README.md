# API Geometry Search - Processamento de Pontos de Interesse

Este repositório contém um **notebook Python** que interage com uma API de pesquisa geográfica para obter, processar e visualizar pontos de interesse (POIs) com base em categorias específicas. A aplicação principal é realizar a análise de dados geográficos e filtrá-los conforme critérios definidos.

---

## Funcionalidades



- **Integração com a API Category Search:**
  - Envia requisições à API para obter categorias de ponto de interesse, baseado em definição de keywords de inclusão/exclusão.
- **Integração com a API Geometry Search:**
  - Envia requisições à API para obter POIs com base em categorias e geometrias definidas.
- **Processamento dos Resultados:**
  - Extração de informações relevantes, como nomes, endereços, categorias e coordenadas.
- **Exportação de Resultados:**
  - Os resultados são organizados em um `DataFrame` e salvos num ficheiro CSV para posterior análise.
- **Visualização Geográfica:**
  - Representação dos POIs num mapa interativo utilizando a biblioteca **Folium**.

---

## Estrutura do Repositório

- **`main.ipynb`**: Ficheiro principal contendo o código completo do projeto.
- **`data/categories_id.csv`**: Ficheiro de saída com os IDs das categorias processadas e filtradas.
- **`README.md`**: Este ficheiro, que documenta o projeto.
- **Outros ficheiros auxiliares**:
  - Ficheiros HTML ou JSON gerados para visualização de dados (se aplicável).

---

## Tecnologias Utilizadas

- **Python 3.x**
- **Bibliotecas**:
  - `requests`: Para interagir com a API.
  - `pandas`: Para manipulação e análise de dados.
  - `folium`: Para criar mapas interativos.

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
API_KEY: Insere a chave de acesso à API.
url e params: Define os parâmetros necessários para a API Geometry Search.
keywords e exclude_keywords: Define as palavras-chave de inclusão e exclusão para o filtro de categorias.
Corre todas as células do notebook para executar o processamento e gerar os ficheiros de saída.

### 3. Resultado
O resultado principal será salvo em data/resultados_pois.csv, contendo informações sobre os pontos de interesse cumprindo os requisitos definidos. 
Se a visualização geográfica estiver ativa, o mapa será gerado no notebook e pode ser exportado para um ficheiro HTML.
