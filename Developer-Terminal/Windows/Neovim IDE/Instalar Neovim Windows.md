Melhor IDE do mundo!!!!

## Instalação do Neovim

Procure no Winget: [winget.run | Finding winget packages made simple.](https://winget.run/)
Link para Neovim: [Download and install Neovim with winget](https://winget.run/pkg/Neovim/Neovim)

Rode o seguinte comando:

``` powershell
winget install -e --id Neovim.Neovim
```

Caso não consiga instalar devido a algum problema com .msi, faça o seguinte:
- Rode um powershell como admin
- Coloque o seguinte comando

```powershell
Invoke-WebRequest -Uri "https://github.com/neovim/neovim/releases/download/v0.11.0/nvim-win64.msi" -OutFile "$env:TEMP\nvim-win64.msi"
Start-Process msiexec.exe -ArgumentList "/i `"$env:TEMP\nvim-win64.msi`" /qn" -Wait
```
