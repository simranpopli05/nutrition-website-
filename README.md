# NUTRITION WEBSITE

## Node Js

**Node.js is a cross-platform, open-source JavaScript runtime environment that can run on Windows, Linux, Unix, macOS, and more. Node.js runs on the V8 JavaScript engine, and executes JavaScript code outside a web browser.**

```
sudo apt update
```
```
sudo apt install nodejs

node -v
```
## NPM

**npm is a package manager for the JavaScript programming language maintained by npm, Inc. npm is the default package manager for the JavaScript runtime environment Node.js and is included as a recommended feature in the Node.js installer.**

```
sudo apt install npm
```

## React vite

**Vite is a modern front-end build tool that provides a faster and leaner development experience for modern web projects. When using React with Vite, you can take advantage of features like:**

###  npm install -g create-vite

```
create-vite my-react-app --template react
```
```
cd my-react-app
```
```
npm run dev
```

## Dependencies

### 1.Bcrypt is a password hashing function that is designed to be computationally expensive, making it more difficult for attackers to brute force the hashed password. It uses a salt to generate a unique hash for each password, which adds an extra layer of security..**

```
npm install bcrypt
```
### 2.CORS stands for Cross-Origin Resource Sharing. It's a mechanism that allows resources (e.g., fonts, JavaScript, etc.) on a web page to be requested from another domain outside the domain from which the resource originated. This is useful for web applications that need to request data from an API hosted on a different domain..**
```
npm install cors
```
### 3. "Express" is a popular web application framework for Node.js. It simplifies the process of building web applications and APIs by providing a set of robust features for handling common web development tasks.


```
npm install express
```


### Docker Docker is a platform for containerization, and Docker containers are lightweight, portable, and executable packages that run your application and its dependencies. Docker images are used to create Docker containers, and Docker networks provide communication and isolation between containers and the host system.

```
sudo apt update
```

```sudo apt install docker.io -y
```
```
sudo systemctl status docker
```
### A Dockerfile is a script that contains instructions for building a Docker image. Here's an example Dockerfile that i have used for my Backend.


```

# Use an official Node.js runtime as a base image
FROM node:20

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install application dependencies
RUN npm install
RUN npm install bcrypt

# Copy the application code to the container
COPY . .

# Expose the port that your application will run on
EXPOSE 3000

# Define the command to run your application
CMD ["node", "index.js"]   
```

### Building docker image 
```
sudo docker build -t backend .
```

### Once the image is successfully built, you can verify whether it is on the list of local images with the command.

```
docker images
```
###Now i have cointaried my backend by using the command given below 

```
sudo docker run -itd --name backend1 -p 3000:3000 backend

```
### After this i have created Dockerfile file for my frontend application 
```
FROM node:20

WORKDIR /app

COPY package*.json ./

RUN npm install

RUN npm i vite

#Ensure vite is installed locally 
#RUN npm install vite 

RUN npm install vite --save-dev
COPY . .

EXPOSE 3000

CMD ["npm","run","dev"]
```
### NOW,we have to follow same steps as we done in backend.












