# analise-de-churn
Projeto de análise de churn com recomendações de ações em CX e CS.

# Resumo do problema (o “briefing”).
A empresa em questão pertence ao ramo de telecomunicação do Irã. O Dataset foi disponibilizado publicamente na comunidade de análise de dados e machine learning Kaggle.

# Objetivos da análise (hipóteses ou perguntas de negócio).
Temos como objetivo compreender os principais fatores que influenciam o churn e desenvolver um modelo preditivo interpretável capaz de estimar a probabilidade de cancelamento a partir de variáveis históricas e comportamentais.A base de dados utilizada é proveniente de uma empresa de telecomunicações iraniana, disponibilizada publicamente na comunidade de Machine Learning Kaggle para fins de experimentação e estudo, sendo amplamente utilizada em grupos de análise de dados e machine learning para testes e demonstrações de metodologias analíticas.

# Descrição do dataset (origem, variáveis, limitações).
O dataset foi encontrado primeiro no site Kaggle (https://www.kaggle.com/datasets/alinoranianesfahani/iranian-churn-dataset) 
Após ser o processo de limpeza, sofreu algumas alterações para uma "atualização" na nomenclatura de algumas colunas do dataset para que melhor refletisse a realidade atual das telecoms, resultando no dataset (telecom_churn_clean.csv).

"Call Failure": "failed_interactions",

"Complains": "support_complaints",

"Subscription Length": "tenure_months",

"Charge Amount": "monthly_spend",

"Seconds of Use": "usage_time_min",   # converter p/ minutos

"Frequency of use": "active_days_per_month",

"Frequency of SMS": "app_notifications_freq",

"Distinct Called Numbers": "unique_interactions"

"Age Group": "age_group",

"Tariff Plan": "plan_type",

"Status": "subscription_status",

"Age": "customer_age",

"Customer Value": "clv",

"Churn": "churn",


# Processo de limpeza.
O processo iniciou com a importação de bibliotecas pandas e numpy, leitura de CVS, padronização de colunas removendo espaços duplicados e espaços no início/fim. Também mapeamos e renomeação de colunas para nomes padronizados (ex acima), conversão de valores numéricos, conversão de segundos para minutos, tratamento de colunas categóricas e criação de mapa etário (18-24, 25-34, etc). Churn se tornou uma categoria binária (0 ou 1), e por fim, antes de exportar uma última versão de (telecom_churn_clean.csv), realizamos um último Sanity Check.

# Principais análises.
CHURN SILENCIOSO: Churn acontece ao longo de falhas de interações, porém ainda apresenta um pico significativo logo no início onde ainda não há interação, demonstrando um "churn silencioso".


<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/561df5b0-2bc0-4c3c-8f78-c7f27478f19d" />


CLIENTES DE BAIXO VALOR: Nos dois gráficos abaixo podemos observar que o churn ocorre mais com Clientes de baixo valor para o negócio.


<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/8269a4ca-57d3-4e89-8539-0beef345187c" />
<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/83b3af81-959d-48f0-8e87-a14b5dcbcc3e" />


BAIXO ENGAJAMENTO: Além de não registrarem (failed_interactions), a maioria dos clientes "churners" também se concentram entre os menos ativos.


<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/840ee029-ed74-4b42-b0a5-1c3edc272579" />
<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/2dc2321b-739b-4f1a-8791-ed01d8b63f1f" />


CLISE DE FIDELIDADE: A descoberta mais grave da análise exploratória foi o grande volume de churn concentrado em clientes de longo prazo, algo que até então parecia ser um problema reservado a novos clientes. Essa informação é mais preocupante pois sugere uma possível erosão do valor do produto, algo para ser investigado com muita atenção. O segundo gráfico desta sessão também aponta o quanto 


<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/92a3d04d-70ec-4d3f-b328-e87cdad7451d" />
<img width="440" height="249" alt="image" src="https://github.com/user-attachments/assets/05e4b549-2e2e-455b-943b-b717a222a837" />


# Modelos aplicados (regressão, árvore, clustering).
REGRESSÃO LOGÍSTICA: O primeiro modelo que realizamos na análise foi o da regressão logística e com dois reajustes para refinamento, ele passou a apresentar os resultados abaixo.

=== Métricas — Modelo Refinado (LogReg) ===

Accuracy : 0.901

A acurácia mostra a performance geral do modelo, ou seja, a porcentagem de previsões que ele acertou no total. Um valor de 89% é um ótimo positivo para a previsão.

Precision: 0.81

A precisão responde à pergunta: "Dos clientes que o modelo previu como Churn, quantos realmente deram churn?". Um valor de 69% é sólido e significa que, para cada 10 clientes sinalizados como de risco, cerca de 7 realmente estão em alto risco.

Recall   : 0.478

O recall responde à pergunta: "De todos os clientes que realmente deram churn, quantos o modelo conseguiu identificar?". Um recall de 59% indica que o modelo é capaz de "pegar" a maioria dos clientes que estão prestes a cancelar.

AUC-ROC  : 0.935

A área sob a curva (AUC-ROC) é uma das melhores métricas para avaliar modelos de classificação. Um valor de 0.935 (em uma escala de 0 a 1) mostra que o modelo é muito bom em distinguir entre clientes de churn e não-churn, superando em muito a aleatoriedade.

F1-score : 0.601

O F1-score sinaliza o balanço entre precisão e recall em um único número. Um F1-score de 0.637 mostra um bom balanço, indicando que o modelo é confiável tanto para identificar clientes em risco quanto para evitar falsos alarmes.


<img width="440" height="372" alt="download" src="https://github.com/user-attachments/assets/28fed273-3215-439e-a544-bc4e168cf6d1" />
<img width="367,96" height="372" alt="download" src="https://github.com/user-attachments/assets/8f771115-55ec-4e33-bda7-ed5ef6aab54f" />





# Resultados e insights (com gráficos finais).

💡 **Conclusão + recomendações práticas**.
