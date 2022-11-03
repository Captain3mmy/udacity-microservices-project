## Build
FROM beevelop/ionic:latest AS ionic
## Create app directory
WORKDIR /usr/src/app
# Install app dependencies
# A wildcard is used to ensure both package.json and package-lock.json are copied where available (npm@5+)
COPY package*.json ./
RUN npm ci
# Bundle app source
COPY . .
RUN ionic build
## Run
FROM nginx:alpine
#COPY www /ur/share/nginx/hml
COPY --from=ionic /usr/src/pp/www sta/usr/share/nginx/html
