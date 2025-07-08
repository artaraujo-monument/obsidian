


- Ficar de olho nas tasks de hotfix pra ver a priorização correta.

- para os DTO's 

web rate -> baseWebRate, Current

 Usually storage facilities will have one rate that they charge for when someone signs up online (web rate) vs. one rate that they charge when someone physically goes to the location to sign up (street rate). 
 
 Adding these two fields on the Create Unit Group modal will help them set the base amount for each type (web & street) so that when they create rate plans and update the pricing for web and street rates they'll have a base amount to calculate from

Toda operação que envolve currency precisa ser convertida pra cents (valor * 100)



street rate for table
```typescript
{
      key: 'currentStreetRate',
      label: 'Street Rate',
      component: ({ row }) => <TableUnitRateCell rate={row.currentRate} />,
    },
```

- Dentro de auth controller, pegar o Portfolio name (a.k.a. DB Prefix) com o @Request req: Request (do express). Com esse domain, eu posso enviar via client metadata. 
- A lambda vai pegar essa prop e vai chamar o internal services API passando esse prefix, passando em qualquer requisição que necessitar (forgotPassword, etc)