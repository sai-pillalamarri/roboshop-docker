FROM  node:20
# creates /app and set the directory to /app
WORKDIR /app
COPY package.json . 
COPY *.js .

# node_modules
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://catalogue:27017/catalogue"
CMD ["node","server.js"]