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

Conclusão
Em uma perspectiva de retenção de clientes, é interessante conseguir prever aqueles com maior potencial de evasão. Sendo assim, o melhor modelo é aquele que possui maior taxa de acerto para churn (True positive ou verdadeiro positivo). Isso se deve ao fato de que, da perspectiva de negócio, é mais fácil e mais barato manter um cliente do que conseguir novos clientes.

Sendo assim, optei por dar maior peso, ou seja, considerar como melhor modelo, aquele que retornou a menor quantidade de falsos negativos, modelo Decision Tree Classifier.

O modelo foi testado com a base de dados balanceado utilizando over-sampling - SMOTE.

A melhor performance se deu aplicando o SMOTE. Apesar do valor baixo para a precisão da variável 1 (churn), o recall melhorou muito, comparado com o resultado obtido com a base sem balanceamento, apresentando o menor número de falsos-positivos dentre as abordagens de balanceamento dos dados e redução dos falsos-negativos.

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
