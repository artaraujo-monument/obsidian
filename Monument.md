
As soon as you convert a lead to a tenant, the balance is 0.

Next month it will be covered.

If it is a recurring service as well. 


6117bec0-fab7-11ef-890f-41d3c9de283d

###  Testndo moveouts

-> Ir em tenants
-> escolher 1
-> More Actions -> moveout
-> selecionr uma reason
-> checar no network o unitRentalRecordUuid e o moveOutReasonUuid. Depois eu deixei no api dog uma rota para fazer testes diretamente no backend, mas o cURL é:

```shell
curl --location --request POST 'http://localhost:3001/tenants/move-out' \
--header 'Content-Type: application/json' \
--data-raw '{
    "unitRentalRecordUuid": "cc03a687-fa00-11ef-b9c4-c1933b4a7e6a",
    "moveOutReasonUuid": "b0a5bad1-fa00-11ef-b9c4-c1933b4a7e6a",
    "paymentOption": "Bad Debt",
    "changeUnitStatusToUnrentable": false,
    "notes": "teste"
}'
```

-> Procurar no banco o resultado: 
```SQL
select BIN_TO_UUID(m.unitRentalRecordUuid, 1) from `moveOut` m order by m.dateCreated desc limit 1;

select *, BIN_TO_UUID(m.unitRentalRecordUuid, 1) from `unitHistoricalRent` m order by m.dateCreated desc limit 1;
```

-> pra completar o moveout tem que coletar o pagamento
-> Executando o pagamento, dispara a request
-> será gerado um recibo que o rafa ta trabalhando
-> Ao optar em enviar o email, deverá ser enviado de acordo com o id do move out
	-> Documento está armazenado em banco, 


-> tem que pegar o unitRentalRecordUuid, utilizar o repositorio do document pra trazer, pegar a URL dele e bater no s3

contactMethod: Email
audience: PastTenant
attachments: { tem que baixar do s3 da amazon e depois transformar 

}


-> Write Off: perdoar divida
-> Collect Payment: pago

-> Cada unit ao enviar um lease se transforma em RESERVED



### Hierarquia do produto

-> Portfolio
	-> Facility
		-> Unit Group
			-> Unit




### Arborstone

- 1 dia do mês é o dia de pagamento das facilities pra eles
- Possuem um sistema de overlock (ver mais sobre)



### PDK

- Gate code <-> Unit Rental Record
- Every gate is connected to a facility segment
	- All units are behind a single gate


> Lead management utils.ts (libs/lead-management)
> internal-services-api/src/leases.controller
> libs/lead-management/src/lead-management.service.ts



Change validation code obligatory:

apps/public-api/src/app/public/facilities/facilities.service.ts - line 166


## Monument

Cognito ID - d380b63d-0ee3-45ea-8914-39e245517538

Facility Segment = grupo
access plan ID = grupo

change on 

line 428: libs/user-management/src/userAccount/user-account.service.ts