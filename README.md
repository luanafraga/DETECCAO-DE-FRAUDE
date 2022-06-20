# DETECCAO-DE-FRAUDE

Projeto Detecção de Fraude

O projeto foi desenvolvido utilizando linguagem Python no Jupyter Notebook. O python possui um série de bibliotecas que nos auxiliam na construção das análises e modelagem dos dados. Neste projeto, foram utilizadas as seguintes:
Pandas
Numpy
Seaborn
Matplotlib
Imbalanced-learn
Scikit-learn

Objetivo

O objetivo deste projeto é a **detecção**, e consequentemente a **diminuição de fraudes**, identificando os **padrões de compra** de cada cliente a partir de informações como nome, cartão de crédito e documentos pessoais.

Dados

A base de dados possui informações sobre:

   - **step**: mapeia uma unidade de tempo no mundo real. Neste caso, 1 passo é 1 hora de tempo. Total de etapas 744 (simulação de 30 dias).

   - **type**: CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER. 
(caixa-de-entrada, caixa-de-saida, débito, pagamento e transferência)

   - **amount**: valor da transação em moeda local.

   - **nameOrig**: cliente que iniciou a transação

   - **oldbalanceOrg**: saldo inicial antes da transação
   
   - **newbalanceOrig**: novo saldo após a transação

   - **nameDest**: cliente que é o destinatário da transação

   - **oldbalanceDest**: destinatário do saldo inicial antes da transação. 

   - **newbalanceDest**: novo destinatário do saldo após a transação. 

   - **isFraud**: São as transações feitas pelos agentes fraudulentos dentro da simulação. 

   - **isFlaggedFraud**: O modelo de negócios visa controlar transferências massivas de uma conta para outra e sinaliza tentativas ilegais. Uma tentativa ilegal neste conjunto de dados é uma tentativa de transferir mais de 200.000 em uma única transação.


Conclusões

Verificamos os seguintes pontos importantes para a **detecção de fraude**:


   - Tipos de movimentação **transferências e cash-out** são os com mais probabilidade de ser uma fraude. **Plano de ação**: Solicitar uma verificação de informação adicional, com uma pergunta de segurança, quando as movimentações forem do tipo transferência ou cash-out;
   
 
   - Tipos de movimentação **pagamento e cash-in** são os com menos probabilidade de ser uma fraude. 
   
   
   - Quando o padrão de compra do cliente é em determinado horário, a transação **fraude costuma ocorrer em período diferente do padrão** (ex: padrão de movimentação pela manhã - fraude pela noite, padrão de movimentação início do mês - fraude final de mês. **Plano de ação**: Uma verificação que pode aumentar a segurança do cliente em horários que não são convencionais.
   
   
   - A grande maioria das fraudes **esvaziam os fundos** do cliente 1, transferindo para outra conta e depois **sacando do sistema.** **Plano de ação**: Solicitar uma verificação de informação adicional, com uma pergunta de segurança, quando o valor da movimentação for igual ao valor total da conta;
   

Após o pré-processamento dos dados, foram criados 3 modelos de machine learning com a biblioteca Scikit Learn: Regressão Logística, Árvore de decisão e Random Forest. Esses modelos foram treinados e avaliados utilizando métricas de avaliação matemáticas e gráficas, para a escolha do melhor modelo. O melhor modelo, o Random Forest, então passou por uma otimização dos hiperparâmetros para que o modelo pudesse ser posto em prática.

O modelo foi testado com a base de dados balanceado utilizando over-sampling - SMOTE.
