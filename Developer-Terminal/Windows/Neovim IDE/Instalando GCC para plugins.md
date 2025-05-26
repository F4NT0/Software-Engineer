Instalamos o seguinte .exe do site [MSYS2](https://www.msys2.org/)

Comando no powershell como admin:

```
Start-Process -FilePath "msys2-x86_64-20250221.exe"  -Verb RunAs 
```

Aceite e instale, assim que terminar ele abre um terminal linux onde iremos rodar o seguinte comado:

```
$ pacman -S mingw-w64-ucrt-x86_64-gcc
```

Depois abra as variáveis de ambiente do windows e altere o __path__ com os seguintes comandos:

```
C:\msys64\bin
C:\msys64\ucrt64\bin
```

Reinicie o terminal e tente o seguinte comando:

```
gcc --version
```