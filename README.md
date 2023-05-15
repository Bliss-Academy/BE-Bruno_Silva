# BE-Bruno_Silva

Guia para utilização da API 
- Funções disponiveis para uso:

- Dashboard
  - dashboard/adduser 
  "id": id na base de dados, implementado de forma automatica ao ser adicionado (não necessita alteração, permanecer 0 por default),
  "userId": id de cada usuario para indentificação (deve ser definido de maneira a ser unico),
  "created": implementado de forma automatica ao ser adicionado (não necessita alteração, permanecer o valor default),
  "updated": implementado de forma automatica ao ser adicionado (não necessita alteração, permanecer o valor default),
  "fname": Primeiro nome do user a ser adicionado,
  "lname": Ultimo nome do user a ser adicionado,
    
  - dashboard/getdashboard/userid
    "userid" = identificador do utilizador
    "TimeFrame" 
       0 = Transações semanais (Weakly)
       1 = Transações Mensais (Mouthly)
       2 = Transações Anuais (Anualy)
       
       
- Transaction
  - transaction/addtransaction
  "userId": indentificador do user a ser atribuido a transação,
  "value": Valor da transação,
  "title": Titulo da transação,
  "description": Descrição da transação,
  "type": Valor inteiro unico, 0 para Income, 1 para expense,
  "attachment": "string" por default
       
  - transaction/gettransactionbyuid/uid/transactiontype
     "uid" =  userid que deseja buscar as transações
     transactiontype
       0 - Income
       1 - Expense
       2 - All (incomes e expenses)
       
  - transaction/gettransactionbyid/id
     id - id da transação na base de dados (visivel ao utilizar o getdashboard, ou gettransactionbyuid)
     
  - transaction/deletetransactionbyid
     id - id da transação a ser deletada da base de dados (devido a bug retorna  200 quando da certo, ou vai abaixo caso não)   
     
  - transaction/updatetransactionbyid
    "id": id da transação na base de dados,
    "userId": userid do dono da transação,
    "created": deve permanecer o default,
    "updated": deve permanecer o default,
    "value": novo valor da transação,
    "title": novo titulo da transação,
    "description": nova descrição,
    "attachment": "string" por default
     
