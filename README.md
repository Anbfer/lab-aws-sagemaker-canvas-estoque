# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

#### Dataset escolhido
- Utilizei o dataset dataset-1000-com-preco-variavel-e-renovacao-estoque.csv para realizar a análise preditiva da variação de preço
- Importei os dados e configuerei as variáveis de entrada e saída.
> Marquei como target o `PRECO`
> Selecionei a coluna identificadora `ID_PRODUTO`
> A coluna responsável pela marcação de tempo `DATA_EVENTO`
> Selecionei o intervalo para previsão dos dados de 9 dias no futuro
> Pedi para que o modelo levasse em consideração os feriados no Brasil para realizar a sua análise
> Os valores ausentes serão substituidos por 0 na coluna `PRECO`
> Os valores ausentes serão substituidos pela mediana na coluna `QUANTIDADE_ESTOQUE`

- Iniciei o treinamento do modelo com o quickbuild
- Após a conclusão tive as seguintes métricas da análise:
>
> ![image](https://github.com/user-attachments/assets/8c7fad9b-30b3-473c-a99e-d9762afed180)
- As seguintes colunas impactaram no resultado da análise:
>
> ![image](https://github.com/user-attachments/assets/3215b33e-ebf0-4fdd-9ad3-646ca62b1c16)

- Usei a opção de gerar as predições única:
> Obtive o seguinte resultado para a predição de preço do produto de ID 1:
>
> ![single_prediction_results](https://github.com/user-attachments/assets/6ee49e2d-4ca1-4044-9d59-038992fc5ebe)

- Com base na demanda histórica, os valores P10, P50 indicam uma queda no preço, para os próximos 9 dias.
- Um ponto de vista mais realista, é condizente com a demanda do produto, que enfrentou uma queda considerável, conforme demonstrado pela linha de demanda histórica.
