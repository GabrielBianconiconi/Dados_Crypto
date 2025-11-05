# 💹 Aplicação de Aprendizado de Máquina na Previsão de Tendências de Criptomoedas

Previsão de tendência (alta ou baixa) para Bitcoin (BTC), Ethereum (ETH) e Solana (SOL) usando Aprendizado de Máquina com dados de mercado e on-chain.

## 🧠 Sobre o Projeto

**Confira o Notebook Colab com o desenvolvimento e treinamento:**
[https://colab.research.google.com/drive/13nrQqhVYulvdQ3Ksn90l0UiuKOH0GnYv?usp=sharing](https://colab.research.google.com/drive/13nrQqhVYulvdQ3Ksn90l0UiuKOH0GnYv?usp=sharing)

Este projeto aplica técnicas de Machine Learning para prever a direção de preço das principais criptomoedas. A solução combina dados de mercado (obtidos via Yahoo Finance) e dados on-chain (via Blockchain.com API) com indicadores técnicos clássicos.

Além da modelagem, o projeto inclui uma aplicação web interativa feita em Streamlit, que permite visualizar gráficos atualizados e obter previsões em tempo real.

## ⚙️ Funcionalidades

* 📈 Coleta automática de dados de mercado (via `yfinance`) e on-chain (via `Blockchain.com API`).
* 🤖 Treinamento de modelos de classificação (XGBoost).
* 💾 Salvamento dos modelos treinados com `joblib`.
* 🌐 Interface interativa em Streamlit para:
    * Escolher a criptomoeda (BTC, ETH, SOL).
    * Atualizar dados e visualizar gráficos de candlestick.
    * Exibir previsão da tendência (Alta/Baixa).
    * Mostrar confiança do modelo e a métrica on-chain correspondente.

## 🤖 Pipeline de Modelagem e Treinamento

O processo de treinamento (executado no script `train_models.py` ou no Notebook Colab) é dividido em quatro etapas principais:

1.  **`get_data_pipeline`**: Orquestra a coleta de dados.
    * Busca os dados de mercado (OHLCV) do **Yahoo Finance** para todas as moedas.
    * **Se** a moeda for BTC, ele também chama a `fetch_onchain_data` para buscar dados da rede (ex: `n-transactions`, `hash-rate`) da API do **Blockchain.com**.
    * Funde os dados em um DataFrame único.

2.  **`create_features_pipeline`**: Realiza a engenharia de features.
    * Calcula indicadores técnicos (RSI, MACD, Bandas de Bollinger, EMAs) usando `pandas-ta`.
    * Cria *features* de *lag* (atraso) e retorno (ex: `Close_lag_7`, `return_1d`) para dar ao modelo um contexto histórico.

3.  **`train_and_save_model`**: Função principal que gerencia o treinamento.
    * **Validação (Teste 80/20):** Primeiro, treina um modelo temporário nos 80% dos dados e o testa nos 20%. Isso serve para gerar as métricas (Matriz de Confusão, Acurácia) e validar se a estratégia é viável.


## ⚙️ Integrantes


* Gabriel Bianconi 20.00822-8
* Bruno Augusto 20.02194-0
* Carlos Alberto Matias 20.01308-6

* Artigo nos arquivos do github:
