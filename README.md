# Projeto Full Exemplo PI

Este repositório contém três projetos diferentes:

1. `app`: Um projeto front-end em React Native.
2. `web`: Um projeto front-end em Vue.js.
3. `backend`: Um projeto back-end em Django REST framework (DRF) com PDM.

## Pré-requisitos

Antes de começar, certifique-se de ter as seguintes ferramentas instaladas em sua máquina:

- [Node.js](https://nodejs.org/) (para o projeto `app` e `web`).
- [Python](https://www.python.org/) (para o projeto `backend`).
- [PDM](https://pdm.fming.dev/): 
- nmcli (para descobrir o IP da sua máquina).
  - Para instalar no Ubuntu: `sudo apt install nmcli`.

## Clonando o Repositório

Para começar, clone este repositório para o seu ambiente local:

```bash
git clone https://github.com/eduardo-da-silva/full-exemplo-pi.git
cd full-exemplo-pi
code .
```

## Projeto `backend` (Django DRF com PDM)

```bash
# Navegue até a pasta do projeto `backend`
cd backend

# Instale as dependências do projeto
sudo apt install python3-dev
pdm install netifaces
```

### Descobrindo o IP da sua máquina

Para que os projetos `app` e `web` possam se comunicar com o projeto `backend`, é necessário descobrir e configurar o IP da sua máquina. 

- Execute o seguinte comando, para descobrir o IP da sua máquina e configurá-lo no arquivo `.env`:

```bash
pdm run set_my_ip.py
```

> **Caso o comando acima não funcione**, você pode descobrir o IP da sua máquina manualmente, e configurá-lo no arquivo `.env`.

- Para descobrir o IP, execute o seguinte comando:

```bash
ipconfig
```

- Coloque o IP descoberto no arquivo `.env`, na variável `MY_IP`.


## Alterando a baseURL

Para que os projetos `app` e `web` possam se comunicar com o projeto `backend`, é necessário alterar a `baseURL` de cada um deles.


Nos projetos `app` e `web`, execute o seguinte comando:

```bash
node set_my_ip.js
```

> **Se não fucionar**, altere manualmente a `baseURL` de cada projeto, colocando o IP da sua máquina.

## Alterando o `package.json`

Para que o projeto `web` possam se comunicar com o projeto `backend`, é necessário alterar o `package.json` dele. 

- Altere a seguinte linha:

```json
   "start": "expo start --port 19000",
```

## Configurando e Executando os Projetos

Aqui estão as instruções para configurar e iniciar cada um dos projetos:

### Projeto `app` (React Native)

```bash
# Navegue até a pasta do projeto `app`
cd app

# Instale as dependências
npm install

# Inicie o aplicativo (certifique-se de que um emulador ou dispositivo esteja conectado)
npm start -- --reset-cache
```

### Projeto `web` (Vue.js)

```bash
# Navegue até a pasta do projeto `web`
cd web

# Instale as dependências
npm install

# Inicie o servidor de desenvolvimento
npm run dev
```

> Certifique-se de seguir as instruções específicas para cada projeto. Após a execução desses comandos, os projetos estarão configurados e em execução em seu ambiente local.
