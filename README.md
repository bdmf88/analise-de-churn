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


# Processo de limpeza (sem expor tudo, mas explicar escolhas).
O processo iniciou com a importação de bibliotecas pandas e numpy, leitura de CVS, padronização de colunas removendo espaços duplicados e espaços no início/fim. Também mapeamos e renomeação de colunas para nomes padronizados (ex acima), conversão de valores numéricos, conversão de segundos para minutos, tratamento de colunas categóricas e criação de mapa etário (18-24, 25-34, etc). Churn se tornou uma categoria binária (0 ou 1), e por fim, antes de exportar uma última versão de (telecom_churn_clean.csv), realizamos um último Sanity Check.

# Principais análises (e por que elas importam).
Churn acontece ao longo de falhas de interações, porém ainda apresenta um pico significativo logo no início onde ainda não há interação, demonstrando um "churn silencioso".
<img width="825" height="467" alt="image" src="https://github.com/user-attachments/assets/561df5b0-2bc0-4c3c-8f78-c7f27478f19d" />

Nos dois gráficos abaixo podemos observar que o churn ocorre mais com Clientes de baixo valor para o negócio.

<img width="825" height="467" alt="image" src="https://github.com/user-attachments/assets/8269a4ca-57d3-4e89-8539-0beef345187c" />
<img width="825" height="467" alt="image" src="https://github.com/user-attachments/assets/83b3af81-959d-48f0-8e87-a14b5dcbcc3e" />



# Modelos aplicados (regressão, árvore, clustering).


# Resultados e insights (com gráficos finais).

💡 **Conclusão + recomendações práticas**.
