# 📈 Análise RFM com Dataset Online Retail

## 🎯 Objetivo do Projeto

Este projeto aplica a metodologia de Recência, Frequência e Valor Monetário (RFM) sobre o [Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail) da UCI Machine Learning Repository. O objetivo é segmentar a base de clientes em grupos distintos com base em seu comportamento de compra (quão recente, frequente e valioso), identificando segmentos chave como 'Campeões', 'Fiéis', 'Em Risco', 'Perdidos', 'Hibernados', etc., para embasar decisões estratégicas de marketing e retenção.

## 🛠️ Tecnologias Utilizadas

* **Python 3.9+** (ou a versão que estiver usando)
* **Polars:** Para manipulação e preparação de dados de alta performance (conforme nossas conversas anteriores). (Se estiver usando Pandas primariamente, ajuste aqui).
* **`ucimlrepo`:** Para buscar o dataset diretamente da UCI via API.
* **Matplotlib & Seaborn:** Para visualização dos dados e resultados da segmentação.
* **Jupyter Lab / Notebook:** Para desenvolvimento e execução interativa da análise.

## ⚙️ Configuração e Instalação

1.  **Clone o repositório (se aplicável):**
    ```bash
    git clone https://github.com/geangobo/rfm_analysis
    cd rfm_analysis 
    ```


2.  **(Recomendado) Crie um Ambiente Virtual:**
    ```bash
    python -m venv venv
    # No Windows:
    venv\Scripts\activate
    # No macOS/Linux:
    source venv/bin/activate
    ```

3.  **Instale as dependências:**
    Certifique-se de ter um arquivo `requirements.txt` no seu projeto que inclua `polars`, `ucimlrepo`, `matplotlib`, `seaborn`, `jupyterlab` (ou `notebook`), etc.
    
    Para instalar os pacotes necessários, execute:
    ```bash
    pip install -r requirements.txt
    ```
    *(Se não tiver o `requirements.txt`, você pode criar um após instalar tudo com `pip freeze > requirements.txt`)*

## ▶️ Execução da Análise

1.  **Dados de Entrada:** Os dados do "Online Retail Dataset" são buscados diretamente da UCI Machine Learning Repository via API usando a biblioteca `ucimlrepo` dentro do notebook. Não é necessário download manual prévio do dataset.
2.  **Execute o Notebook:** Abra o Jupyter Lab ou Jupyter Notebook, navegue até a pasta `src/` e execute as células do notebook principal (ex: `rfm_analysis_notebook.ipynb` - *substitua pelo nome real do seu notebook*). O notebook guiará pelo processo de:
    * Busca dos dados.
    * Pré-processamento e limpeza.
    * Cálculo das métricas e scores RFM.
    * Segmentação dos clientes.
    * Geração de visualizações.
3.  **Resultados:** O processo irá gerar:
    * Logs e saídas diretamente no notebook.
    * Visualizações gráficas (ex: Treemap, gráficos de barras, histogramas).
    * (Opcional) Um arquivo de saída (ex: `.csv` ou `.parquet`) com o DataFrame final contendo os clientes e seus respectivos segmentos RFM, se implementado no código.

## 💡 Conceitos Chave

* **RFM (Recency, Frequency, Monetary Value):** 🔑 Técnica para segmentar clientes baseada no histórico de compras:
    * **Recência (R):** ⏱️ Tempo desde a última compra (Menor = Melhor).
    * **Frequência (F):** 🔄 Número de compras em um período (Maior = Melhor).
    * **Valor Monetário (M):** 💰 Gasto total no período (Maior = Melhor).
* **Pontuação/Scoring RFM:** 🔢 Atribuição de notas (ex: 1-5 ou A-E) para cada dimensão RFM, geralmente baseada em quantis (ex: quintis), para comparar clientes em uma escala comum e relativa à base de dados.
* **Segmentação RFM:** 🧩 Agrupamento de clientes com base em seus scores RFM combinados para criar personas acionáveis (ex: Campeões, Fiéis, Atenção, Em Risco, Perdidos, etc.), permitindo ações de marketing e relacionamento mais direcionadas.

## 📊 Exemplos de Visualizações Geradas

* **Treemap:** Visualização da distribuição dos segmentos de clientes (ex: por Valor Total Gasto ou por Contagem de Clientes em cada segmento).
* **Gráficos de Barras:** Contagem de clientes por segmento RFM ou valor médio por segmento.
* **Histogramas/Boxplots:** Análise da distribuição das métricas R, F e M para cada segmento.
* **Gráficos de Dispersão:** Relação entre Recência vs Frequência ou Frequência vs Valor, coloridos por segmento RFM.