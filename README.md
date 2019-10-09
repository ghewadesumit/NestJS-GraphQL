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

# Schema First
* To start using schema first way, simply add typePaths array inside the options object.
 * Open **app.module.ts** and make the following changes
 
 ```
import { Module } from '@nestjs/common';
import { AppController } from './app.controller';
import { AppService } from './app.service';
import { GraphQLModule } from '@nestjs/graphql';
import { join } from 'path';

@Module({
 GraphQLModule.forRoot({
  typePaths: ['./**/*.graphql'],
  playground: true
}),
 ],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}

```

* Lets say you want to create a graphql project to store the data for "Users" then we have to create Module, Resolver and Service files. These files can be created using the following command.

* For Reference
 * nest generate: Generates and/or modifies files based on a schematic
   ```
    nest generate <schematic> <name> [options]
    nest g <schematic> <name> [options]
   ```
* For detailed list of CLI command visit https://docs.nestjs.com/cli/usages
### CLI commands for Nest are as follows:
 * For Creating Module:
 ```
 nest g mo user
 ```
 * For creating Resolver:
 ```
 nest g r user
 ```
 * For creating Service
 ```
 nest g s user
 ```
* After executing the above commands you will get a user folder. In this user folder create a graphql file.
 * for example: **user.graphql**

# Demo for Hello World!
 
* Add the following code to **user.graphql**
```
type Query{
hello: String!
}
```

* Add the following code to **user.resolver.ts**

```
import { Resolver, Query, Args } from '@nestjs/graphql';

@Resolver('User')
export class UserResolver {
    @Query(()=>String)
    async hello(){
        return hello;
    }
```

***Notes:-***
1) Resolver adds the data to the graphql.
2) The type of query should be specified in the declarative '@'.
  * In our case the type is query in graphql so to add data, we use **@Query** in resolver.
3) We use async function named after the name of attribute in the **graphql**.
  * In our case the attribute name is **hello**, so the function name in **Resolver** will be **hello()**. 
  
### Execute the Project

* Go to Terminal and use the command
```
yarn start
```

* Go the browser and enter http://localhost:3000
* To test the graphql query use:- http://localhost:3000/graphql

          
 
 


