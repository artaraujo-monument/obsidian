
basically to run any app on [[Monument]] just use

`npx nx run operations-suite:serve:local` for the front end 
`yarn start:debug` for the back end monument-api


Ao alterar um DTO, é preciso rebuildar a api pra que seja gerado o arquivo correspondente.

Ao alterar qualquer coisa que envolva o backend, tem q rodar os smoke tests pra ver se as fixtures estão ok, pois pode quebrar forte.



### Unit group

24cf0412-96f7-11ef-946a-7be0f5fbdd36