---
title: Installation Instructions
date: 2019-06-18 06:40:12
---

# Installation Instructions
::: warning COMPATIBILITY NOTE
Vue Fullstack Generator requires Node.js >= 10.x
:::

## Softwares Required
### Install
Download and install the following softwares
- [NodeJS (Web Server)](https://nodejs.org/en/)
- [MongoDB (Database)](https://www.mongodb.com/)
- [Yarn](https://yarnpkg.com/en/docs/install)
- [Python 2.7](https://www.python.org/downloads/release/python-2715/)

OR through terminal
``` bash
# For Windows
choco install nodejs mongodb yarn python2
# OR for linux
sudo apt-get install nodejs mongodb yarn python2
```

#### Node Gyp
We also need node-gyp installed. Please follow the steps to install it
[https://github.com/nodejs/node-gyp#installation](https://github.com/nodejs/node-gyp#installation)

### Start database
Start mongodb in a separate shell
Run the follwoing commands from an elevated termnial/command prompt. <br/>

In Windows operating system we can start it by opening the following file.
  ``` bash
  C:/Program Files/MongoDB/Server/3.2/bin/mongod.exe
  ```  
In Linux operating system we can start it by 
  ``` bash
sudo apt-get install -y mongodb-org
sudo service mongod start
OR
sudo systemctl enable mongod.service
  ```  

## Installation (Local)
Download and unzip the file from codecanyon and navigate inside the directory

``` bash
cd generator-vuefull
```

### Prepare the generator
  This will install the required node dependencies and prepare the generator 
  ``` bash
yarn
yarn link
  ```  

```
``` bash
cd generator-vuefull/vuefull-api
```
### Start server
  This will install the required node dependencies and start the Server(API) at [http://localhost:9090](http://localhost:9090)
  ``` bash
yarn
yarn dev
  ```  

``` bash
cd generator-vuefull/vuefull-client
```
### Start client
  This will install the required node dependencies and start the Client(Vuefull Admin Panel) at [http://localhost:3030](http://localhost:3030) 
  ``` bash
yarn
yarn dev
  ```  
**That's it !!!**

Now open [http://localhost:3030](http://localhost:3030) (Vuefull Admin Panel)


## Installation (Production)

<img src="./img/deploy.png" alt="deployment"/>

### Generate and copy
Add your logo/icon(512px*512px) to static directory (This step is essential to generate icons for Progressive Web App)

The follwing command will generate both client and server files inside `prod` directory which can be directly copied to production server
  ``` bash
yarn prod
  ```  
Now copy the files inside `prod` directory to the production server (Separately for both admin panel and server)

### Start the app
Login to cloud shell and run the `server`
  ``` bash
  cd /var/www/vuefull-api
  npm start
  ```  
Start another cloud shell and run the `client`
  ``` bash
  cd /var/www/vuefull-client
  npm start
  ```  
