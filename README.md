# NestJS-GraphQL
Creating a backend server to store the users data

First install Visual Studio Code from https://code.visualstudio.com/download

* Then Install Node.js from https://nodejs.org/en/
  * Select the LTS version which is recommended for most of the user.
  
* Open Visual Studio Code  and create a folder and open Terminal -> go to the directory you just created.
  * Yarn is used to download and install packages and most of the developer uses it because it is relatively faster than npm.
  * Again its your choice whether you want to use npm or yarn to install packages and dependencies.
  
```
npm install --save yarn-install
```

* To check yarn version type 
```
yarn --version
```
# Installing NestJS

* you can use following command
  * For npm users
  ```
  npm i -g @nestjs/cli
  ```
  * For yarn users
  ```
  yarn add global @nestjs/cli
  ```
  
# Create the NestJs Project
```
nest new project-name
```
* For Example if want to create a project named alpha
```
nest new alpha
```

# Installing graphql

* Once we have created the project then go to project directory and use the following command to install GraphQL
  * For npm users
  ```
  npm i --save @nestjs/graphql apollo-server-express graphql-tools graphql
  ```
  * For yarn users
  ```
  yarn add global @nestjs/graphql apollo-server-express graphql-tools graphql
  ```
* Nest offers two ways for building the GraphQL application
  * Schema first
  * Code first

* Here we will learn how to do Schema first

