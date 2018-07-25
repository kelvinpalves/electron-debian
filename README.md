# Electron + SerialPort + Instalador .deb

## Módulos necessários

### SerialPort

Node-SerialPort fornece uma interface para trabalhar com portas seriais de baixo nível.

> npm install --save serialport

### Electron

Framework para criação de aplicações nativas utilizando tecnologias web como Javascript, HTML e CSS.

> npm install --save-dev electron

### Configurando 

Instalar o electron-rebuild e recompilar o pacote da porta serial de acordo com a versão do node utilizada pelo Electron.

Instalar:

> npm install -g electron-rebuild

Recompilar:

> electron-rebuild

### Gerar pacote .deb (Instalador para sistemas deverivado da distro Debian)

Para gerar o pacote é necessário ter dois módulos instalados:

* electron-packager (Gera um pacote baseado na aplicação para o sistema operacional e arquitetura desejada)
* electron-installer-debian (Cria o instalador baseado no pacote gerado pelo electron-packager)

#### Instalação

Instalar gerador de pacotes:
> npm install -g electron-packager

Instalar gerador de instalador:
>npm install -g electron-installer-debian

#### Geração

Gerar o pacote:
> electron-packager . electron-debian --platform linux --arch x64 --out release-build --electron-version 2.0.5

Gerar o instalador:
> electron-installer-debian --src release-build/electron-debian-linux-x64 --dest release-build/ --arch x64

