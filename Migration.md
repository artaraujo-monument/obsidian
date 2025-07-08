he 
Na troca de uma entidade

`yarn migration -g <nome>`

Depois pra rodar local tem que rodar com yarn migration -r <nome_do_tenant>

`yarn migration -r sourceOfTruth`

pra rodar em dev, precisa desse prefix no query param:

[https://internal-services-api.dev.monument.io/migration/runMigrations/?databasePrefix=development](https://internal-services-api.dev.monument.io/migration/runMigrations/?databasePrefix=development)

### Criando uma migration nova

Pra algumas mudanças, há uma geração muito grande de coisas desnecessárias. Sempre bom limpar 

Para gerar uma nova:

`yarn migration --generate <nome>`

Ele gera em: libs/migrations/migrations, mas pra gerar, é preciso estar no banco em cloud:

no seu .env, descomente o banco em cloud e comente o local:

```shell
MYSQL_HOST=mysql-001.prv.dev.monument.io
MYSQL_PORT=3306
MYSQL_USER=arthur_araujo
MYSQL_PASSWORD=Wwh1RiHXWGUer3SRXJ
MYSQL_PASS=Wwh1RiHXWGUer3SRXJ

# MYSQL_HOST=127.0.0.1
# MYSQL_PORT=3306
# MYSQL_USER=root
# MYSQL_PASSWORD=thecrew # To be removed
# MYSQL_PASS=thecrew
```

### Rodando migration

É possível rodar uma migration em development de 2 formas

#### Usando yarn -r

apontando o .env para o banco em cloud, podemos executar o comando `yarn migration -r <nome do banco>`.

## Gate Creation

- create the gate on PDK, then on our database
- we connect the gate to the facility segment by using the vendor middle table. We will have the segment ids for this one.
	- In the intermediate table, we have the access vendor access zone id - the id of the access plan in PDK (which is a group)
- Access groups for monument are both groups and time hours available for each gate. For PDK, they're specifically the groups

segment N:N gate


## Creating a new DB

FIXTURE_DATA=SMALL yarn migration --createSourceOfTruth