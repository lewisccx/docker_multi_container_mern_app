FROM node:16-alpine3.15

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 3000

CMD ["npm", "start"]

# docker build --tag goals_frontend_node:dev .
# add goals_frontend_app to a network
# change localhost to goals_backend_app in app.js
# docker run --name goals_frontend_app -p 3000:3000 --rm -d -it --network goals-net goals_frontend_node:dev

# app will run into error as react app run in browser, and local browser does not
# understand http://goals_backend_app/goals in app.js\
# change back to localhost 
# publish port 80 on your backend app

# or just run 
# docker run --name goals_frontend_app -p 3000:3000 --rm -d -it -v C:\Users\1700559\Documents\docker\samples\multi_container_mern_app\frontend\src:/app/src -v /app/node_modules goals_frontend_node:dev

# to enable live update
# have to create project on WSL2 distribution on Windows or
# use "WATCHPACK_POLLING=true react-scripts start" in package.json
