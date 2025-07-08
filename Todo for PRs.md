
- Assign to me
- Check which team must approve. If not capybaras, send on #engineering slack channel.

### Using the VPN

-> Navigate to Configs on Desktop
-> use `wg-quick up MonumentArthur.conf`


### Sending to Dev

Github Actions

Release -> Run workflow for the application affected.

To test on dev (needs vpn) -> [https://monument.dev.monument.io/login](https://monument.dev.monument.io/login)

Staging -> [https://monument.stg.monument.io/](https://monument.stg.monument.io/)
Then move the card to QA after testing

Before sending to QA, we fill Bug Caused By and Root Cause.

When the person does not exist anymore, I'll put Darby Hadley on Bug Caused By

#### User e senha de dev

```json
{
  "username": "test.dev@monument.io",
  "password": "AbcD_1234"
}
```

### Hotfix

- Use the most recent RC 
- Then, open a branch from it

### On Dev

Tem que pedir pro ivan usuario e senha

### On prod

on deployments, all migrations are ran
 
Os bancos são diversos, mas só o development_Monument é necessário de consultar se estiver testando na URL. O restante é só para apontar.