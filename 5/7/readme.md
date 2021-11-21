# Deployment 


1.Backend 

  * Docker file
    backend2
    ```
    FROM node:lts-alpine3.14

    WORKDIR /usr/src/app/housy-backend2
    COPY package*.json ./

    RUN npm install
    RUN npm i -g sequelize
    RUN npm i -g sequelize-cli
    RUN npm i mysql2 -g
    COPY . .
    RUN sequelize db:migrate

    EXPOSE 5000
    CMD [ "npm","start" ]
    ```
    
    isi config.json for backend2
    ```
    {
    "development": {
     "username": "root",
     "password": "alsangar123",
     "database": "housy2",
     "host": "54.224.243.18",
     "dialect": "mysql"
    },
    "test": {
     "username": "root",
     "password": null,
     "database": "database_test",
     "host": "127.0.0.1",
     "dialect": "mysql"
    },
    "production": {
     "use_env_variable": "52.224.243.18",
     "dialect": "postgres",
     "protocol": "postgres"
     }
    }
    ```
    Build
    
    ![dp1](https://user-images.githubusercontent.com/90166916/142759049-7d34fe80-51cb-459c-94a0-3d3d572d3c60.png)

    Hasil migrate 
    
    ![migrate1](https://user-images.githubusercontent.com/90166916/142759055-686c4193-a4ff-4242-a82d-00fc67746a25.png)

    Docker file backend1
    ```
    FROM node:10
   
    ENV DATABASE_URL postgresql://postgres:postgres@54.224.243.18:5432/housy

    WORKDIR /usr/src/app/housy-backend
    COPY . .

    RUN npm install
    RUN npm install -g sequelize-cli
    RUN npx sequelize db:migrate

    EXPOSE 5000
    CMD ["node", "index.js"]
    ```
    isi config.json for backend1
   
   ```
    {
     "development": {
      "username": "postgres",
      "password": "alsangar123",
      "database": "housy",
      "host": "54.224.243.18",
      "dialect": "postgres"
    },
    "test": {
      "username": "root",
      "password": null,
      "database": "database_test",
      "host": "127.0.0.1",
      "dialect": "mysql"
    },
    "production": {
    "use_env_variable": "52.224.243.18",
    "dialect": "postgres",
    "protocol": "postgres"
      }
    }
   ```
   Build
   
   ![dp3](https://user-images.githubusercontent.com/90166916/142758846-a257db20-36bb-41ed-9e42-27e276b2908d.png)

   ![dp4](https://user-images.githubusercontent.com/90166916/142758844-089a6ae1-d06e-403a-9e9f-7fe1e3b215f8.png)
   
   Hasil migrate
   
   ![migrate2](https://user-images.githubusercontent.com/90166916/142759159-fc96dbd8-7999-4689-84fb-d86559d4923c.png)

2. Frontend.

  * Docker file frontend2

  ```
  FROM node:14

  WORKDIR /usr/src/app/housy-frontend1
  COPY . .

  RUN npm install 
  RUN npm install serve -g

  EXPOSE 3000
  CMD ["npm","start"]
  ```
  isi api.js
  ```
  import axios from "axios";

  // Set config defaults when creating the instance
  export const API = axios.create({
    baseURL: "http://35.175.53.239:5555/",
  });

  // Alter defaults after instance has been created
  export const setAuthToken = (token) => {
    API.defaults.headers.common["Authorization"] = `Bearer ${token}`; 
  };
  ``` 
  build
  
  ![dp5](https://user-images.githubusercontent.com/90166916/142759503-4222b1e9-6d01-48b8-aa15-68e16c9cef12.png)

  ![dp6](https://user-images.githubusercontent.com/90166916/142759502-d6585b5e-d3f0-4621-81bb-e2a79721db27.png)

 * Dockerfile frontend1

  ```
  FROM node:14

  WORKDIR /usr/src/app/housy-frontend
  COPY . .

  RUN yarn install
  RUN yarn build

  EXPOSE 3000
  CMD ["yarn", "run", "start"]
  ```
  isi api.js
  ```
  import axios from "axios";

  // Set config defaults when creating the instance
  export const API = axios.create({
    baseURL: "https://api.alvin.onlinecamp.id/",
  });

  // Alter defaults after instance has been created
  export const setAuthToken = (token) => {
    API.defaults.headers.common["Authorization"] = `Bearer ${token}`;
  };
  ```
  build
  
  ![dp7](https://user-images.githubusercontent.com/90166916/142759688-a99ea793-feec-4c3a-ba6c-9baa8522cab8.png)

  ![dp8](https://user-images.githubusercontent.com/90166916/142759687-30b0ec42-8fe5-441c-915b-f46208c60165.png)

# Acces to web Server

  1.Backend
    *backend2 dan backend1
    
    `sudo docker container create --name backend2 -p 5555:5000 housy-backend2`
    
    `sudo docker container start backend2`
    
    `sudo docker container create --name backend -p 5000:5000 housy-backend`
    
    `sudo docker container start backend1`
  
  2. Frontend
   *fronend2 dan frontend1
   
    `sudo docker container create --name frontend2 -p 3333:3000 housy-frontend2:latest`
    
    `sudo docker container start frontend2`
    
    `sudo docker container create --name frontend1 -p 3000:3000 alvin/housyfrontend:latest`
    
    `sudo docker container start frontend1`
    
   ![dp9](https://user-images.githubusercontent.com/90166916/142759966-47c64275-19f1-431f-9f2a-ceef0136e630.png)

   ![dp10](https://user-images.githubusercontent.com/90166916/142760054-9f5edc2b-2ab8-4b03-b392-e6e8b23f1cda.png)

   ![dp11](https://user-images.githubusercontent.com/90166916/142760053-45a02c4b-dbed-4c17-89d2-0c95dfd716d2.png)

   ![dp13](https://user-images.githubusercontent.com/90166916/142760050-859714f9-5cbe-45d0-937e-7b152a11327a.png)

   ![dp12](https://user-images.githubusercontent.com/90166916/142760052-74f57f9b-7387-4bb3-8b66-20c02b7b9032.png)
