# Quanto vale esta casa?

App em Streamlit que estima o preço de venda de uma casa em Ames (Iowa, EUA). Você preenche oito
características da casa, e o modelo devolve o preço previsto, em dólares.

App publicado em: https://SEU-APP.streamlit.app

## Os arquivos

| arquivo | o que faz |
|---|---|
| `app.py` | a tela: carrega o modelo, mostra o formulário e calcula o preço |
| `modelo_casas.pkl` | o pipeline treinado (preenchimento, escala, codificação e o modelo Ridge) |
| `requirements.txt` | as bibliotecas que o Streamlit instala antes de rodar o app |
| `README.md` | esta página |

## O modelo

É o pipeline da Aula 11 de INF1032 (PUC-Rio), treinado com as 1.460 vendas do conjunto Ames Housing
(De Cock, 2011), de 2006 a 2010. Ele usa cinco colunas numéricas (`OverallQual`, `GrLivArea`,
`TotalBsmtSF`, `LotArea`, `GarageCars`) e três categóricas (`Neighborhood`, `HouseStyle`,
`ExterQual`). As áreas do Ames estão em pés quadrados; o app pede em metros quadrados e converte
antes de chamar o modelo.

O `requirements.txt` fixa a versão do scikit-learn que gerou o arquivo `.pkl`, porque com outra o
arquivo pode não carregar, e a versão do Streamlit com que o app foi testado.

## Rodar no seu computador

```bash
pip install -r requirements.txt
streamlit run app.py
```

O preço é uma estimativa do modelo, não uma avaliação do imóvel.
