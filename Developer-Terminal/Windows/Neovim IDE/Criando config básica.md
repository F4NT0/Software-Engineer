#nvim

## Criando arquivo init.lua

Após [[Instalar Neovim Windows]] devemos ir até o diretório de configuração do Neovim, que fica no seguinte local, se não existir crie um diretório chamado **nvim** no Local, como abaixo:

```
C:\Users\{usuario}\AppData\Local\nvim
```

Agora dentro desse diretório iremos criar um arquivo chamado __init.lua__ que vai ser nosso ponto de partida na configuração da nossa IDE.

```powershell
New-Item -Path .\init.lua -ItemType File
```

![[Pasted image 20250402193017.png]]

Vamos abrir o arquivo e adicionar nossas configurações, onde iremos abrir no Neovim:

```powershell
nvim init.lua
```

Podemos criar comentários usando _--_ como no exemplo abaixo

![[Pasted image 20250402193225.png]]

Podemos colocar configurações do VIM utilizando o método _vim.cmd()_ e o comando VIM que queremos, após colocar o que quisermos, salvamos com __:w__ e depois usamos o comando __:source %__ para atualizar nossa configuração básica.

