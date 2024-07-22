# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Bem-vindo ao desafio de projeto "Previsão de Estoque Inteligente na AWS com SageMaker Canvas. Neste Lab DIO, você aprenderá a usar o SageMaker Canvas para criar previsões de estoque baseadas em Machine Learning (ML). Siga os passos abaixo para completar o desafio!

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter uma conta na AWS. Se precisar de ajuda para criar sua conta, confira nosso repositório [AWS Cloud Quickstart](https://github.com/digitalinnovationone/aws-cloud-quickstart).


## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

- Dê um fork neste projeto e reescreva este `README.md`. Sinta-se à vontade para detalhar todo o processo de criação do seu Modelo de ML para uma "Previsão de Estoque Inteligente".
- Para isso, siga o [passo a passo] descrito a seguir e evolua as suas habilidades em ML no-code com o Amazon SageMaker Canvas.
- Ao concluir, envie a URL do seu repositório com a solução na plataforma da DIO.


## 🚀 Passo a Passo

### 1. Selecionar Dataset

-   Navegue até a pasta `datasets` deste repositório. Esta pasta contém os datasets que você poderá escolher para treinar e testar seu modelo de ML. Sinta-se à vontade para gerar/enriquecer seus próprios datasets, quanto mais você se engajar, mais relevante esse projeto será em seu portfólio.
-   Escolha o dataset que você usará para treinar seu modelo de previsão de estoque.
-   Faça o upload do dataset no SageMaker Canvas.

### 2. Construir/Treinar

-   No SageMaker Canvas, importe o dataset que você selecionou.
-   Configure as variáveis de entrada e saída de acordo com os dados.
-   Inicie o treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

### 3. Analisar

-   Após o treinamento, examine as métricas de performance do modelo.
-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.

### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.



## Meu Projeto Previsão de Estoque Inteligente na AWS com SageMaker Canvas

DESAFIO: modelo treinado para fazer previsões de estoque.

CASE: modelo que avalia a quantidade de produtos em estoque, considerando a situação  promocional.

PREVISÃO FUTURA: como ficará o estoque dos produtos no futuro, com base nos dados históricos.

DATASET
O dataset possui 25 identificadores de produtos diferentes, no qual apresenta o dia de atualização de seu estoque; sua situação promocional e a quantidade em estoque. Sendo considerado a sua variação por dia consecutivo, dentro de 20 dias contados desde o seu registro.

Colunas do dataset:
ID_PRODUTO –  identificador do produto
DIA –  	data de atualização do estoque 
FLAG_PROMOCAO – situação promocional (1) em promoção e (0) não está em promoção	
QUANTIDADE_ESTOQUE -> quantidade de produtos em estoque (target)

MODELO
O modelo foi treinado através do Quick Build; priorizando a velocidade. Sendo possível obter o seguinte model status:
Descrição:

Avg.wQL (Média Perda Quantil Ponderada) = 0.086 significa que o modelo tem um bom desempenho ao prever a distribuição dos estoques, com um valor relativamente baixo de perda de quantil ponderada.

MAPE (Erro Percentual Médio Absoluto) = 0.290 ou 29% significa que, em média, as previsões do modelo diferem dos valores reais por 29%. Isso fornece uma medida de precisão relativa, indicando que as previsões têm um erro médio de 29% em relação aos valores reais.

WAPE (Erro Percentual Absoluto Ponderado) = 0.152 ou 15.2% indica que, considerando a quantidade total dos valores reais, o erro percentual absoluto médio ponderado é de 15.2%, Isso sugere que, em média, o modelo está errando 15.2% quando ponderamos os erros pela magnitude dos valores reais.

RMSE (Raiz do Erro Quadrático Médio) =  1.535 indica que a magnitude dos erros de previsão é de aproximadamente 1.535 unidades de estoque. 

MASE (Erro Escalado Médio Absoluto) = 0.180 significa que o erro absoluto médio das previsões do modelo é 18% do erro absoluto médio de um modelo de referência simples, como a média móvel. Um valor menor que 1 indica que o modelo de previsão é melhor que o modelo de referência. Neste caso, 0.180 é um valor muito bom, mostrando que o modelo tem um desempenho significativamente melhor.

ANÁLISE PREDITIVA
Para a análise do estoque, foi considerado o fator promocional dos produtos, visto que nessa situação é crucial evitar rupturas de estoque, mesmo que isso signifique ter um estoque maior que o necessário na maioria dos casos; sendo assim, utilizado o P90 (90º Percentil) que representa um cenário onde apenas 10% das previsões são maiores que este valor, indicando que está se preparando para quase todos os cenários de alta demanda.
Durante a análise foi escolhido identificadores de 5 produtos diferentes (IDs 1, 5, 6, 16 e 24 ), no qual possuem frequências promocionais diversas, bem como quantidade em estoque. 

O produto de ID 1:
Registro de estoque (2023-12-31): 91 unidades; 
Esteve em promoção 6 vezes;
Demanda histórica (2024-01-19): 16 unidades;
2024-01-20 P90 de aproximadamente 13 unidades.

O produto de ID 5:
Registro de estoque (2023-12-31): 95 unidades; 
Esteve em promoção 3 vezes;
Demanda histórica (2024-01-19): 21 unidades;
2024-01-20 P90 de aproximadamente 21 unidades.

O produto de ID 6:
Registro de estoque (2023-12-31): 56 unidades; 
Esteve em promoção 2 vezes;
Demanda histórica (2024-01-19): 0 unidades;
2024-01-20 P90 de aproximadamente 0 unidades.

O produto de ID 16:
Registro de estoque (2023-12-31): 97 unidades; 
Esteve em promoção 2 vezes;
Demanda histórica (2024-01-19): 33 unidades;
2024-01-20 P90 de aproximadamente 32 unidades.

O produto de ID 24:
Registro de estoque (2023-12-31): 56 unidades; 
Esteve em promoção 4 vezes;
Demanda histórica (2024-01-19): 0 unidades;
2024-01-20 P90 de aproximadamente 0 unidades.

CONCLUSÃO
Logo, o modelo apresentou resultados satisfatórios. De modo que apresenta ser eficaz na gestão de estoques em contextos promocionais, permitindo a otimização dos níveis e minimização de rupturas a partir do P90 (90º percentil).  
Sendo possível observar a influência das promoções na demanda: o produto ID 1 e produto ID 5 estiveram em promoção diversas vezes e apresentam uma demanda preditiva significativa. Isso mostra que as promoções têm um impacto direto na demanda desses produtos, apresentando a necessidade de manter os níveis de estoque adequados para que evite futuras rupturas.




