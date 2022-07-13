FROM node:16-alpine3.15

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 80

ENV MONGODB_USERNAME=mongoadmin
ENV MONGODB_PASSWORD=password

CMD ["npm", "start"]


# docker build --tag goals_backend_node:dev .
# docker run --name goals_backend_app -p 80:80 -d goals_backend_node:dev 
# added backend to a network
# -p 80:80, publish port in optional here unless u want to access backend from your localhost:80
# docker run --name goals_backend_app --rm -d -p 80:80 --network goals-net goals_backend_node:dev 

# to persist data for logs folder 
# docker run --name goals_backend_app --rm -d -p 80:80 -v logs:/app/logs --network goals-net goals_backend_node:dev

# to enable live preview, add bind mount
# docker run --name goals_backend_app --rm -d -p 80:80 -v "C:\Users\1700559\Documents\docker\samples\multi_container_mern_app\backend":/app -v logs:/app/logs -v /app/node_modules --network goals-net goals_backend_node:dev

# to dynamically inject mongodb username and password
# docker run --name goals_backend_app --rm -d -p 80:80 -v "C:\Users\1700559\Documents\docker\samples\multi_container_mern_app\backend":/app -v logs:/app/logs -v /app/node_modules --network goals-net -e MONGODB_USERNAME=mongodbadmin -e MONGODB_PASSWORD=password goals_backend_node:dev
