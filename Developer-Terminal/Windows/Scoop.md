#management

Instalador de pacotes para windows

## Instalação

Abra um terminal e rode o seguinte comando:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

Deve aparecer o seguinte resultado no terminal:

![[Pasted image 20250331074340.png]]
