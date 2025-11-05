# 💹 Aplicação de Aprendizado de Máquina na Previsão de Tendências de Criptomoedas

Previsão de tendência (alta ou baixa) para Bitcoin (BTC), Ethereum (ETH) e Solana (SOL) usando Aprendizado de Máquina com dados de mercado e on-chain.

## 🧠 Sobre o Projeto

https://colab.research.google.com/drive/13nrQqhVYulvdQ3Ksn90l0UiuKOH0GnYv?usp=sharing

Este projeto aplica técnicas de Machine Learning para prever a direção de preço das principais criptomoedas. A solução combina dados de mercado (obtidos via Yahoo Finance) e dados on-chain (via Blockchain.com API) com indicadores técnicos clássicos como RSI, MACD, EMA e Bandas de Bollinger.

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


## ⚙️ Dados


  * Yahoo Finance API (via yfinance)

  * Blockchain.com API (via integração direta)
