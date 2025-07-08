
### Conventional Tasks

- [ ] Take a look at the template for alerting https://docs.newrelic.com/docs/alerts/create-alert/condition-details/alert-custom-incident-descriptions/#create-description
	- [ ] NR Links
		- [ ] https://docs.newrelic.com/docs/nrql/nrql-syntax-clauses-functions/#with-as-nrql-var
		- [ ] https://docs.newrelic.com/whats-new/2022/10/whats-new-10-13-nrql-productivity-improvements/
		- [x] **SOLUTION: Enriched query on alert**
			- [ ] Check if we can do a "if error 500 find on internal-services-api"
- [ ] Double check NR alerts for Move Outs
	- [ ] Will have to change from Log_Error to Log with error level
- [ ] Do more Dashes for things I've worked
	- [ ] Converted leads, for example
- [ ] Log db prefix to help easier investigation when logging on lambda communications

### Bug Bash - 19/05

- [x] Lead showing up -> line 619 

### GIM tasks

### Vendor access rule

- Criar a rule no PDK
	- Formato:
	
```json
{
  "type": "access",
  "allow": true,
  "devices": [
    "35347d04-a99c-4a58-ab32-1317b832507a"
  ],
  "authenticationPolicy": "cardOrPin",
  "startTime": "09:00",
  "stopTime": "17:00",
  "recurring": [
    "Mon",
    "Tue",
    "Wed",
    "Thu",
    "Fri"
  ]
}
```


- [x] Checar se existe a criação da rule no vendor provider
- [x] Checar o save no banco de dados

### Table Access Plan and related

- [ ] Change accessPlanRepository libs/gate-integration/src/Database/repositories/accessPlan.repository.ts to make inner joins with item type or else item will always be null.

### Application General Security

Helmet is currently too opened for global use. Seems that we need to fix this by adding some new headers to helmet on [[monument-api]]  `main` file. 