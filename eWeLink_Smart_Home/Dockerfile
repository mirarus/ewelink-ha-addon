# ARG BUILD_FROM
# FROM $BUILD_FROM

FROM node:20-bookworm
ENV CK_API_ENV=prod
RUN apt-get update && apt-get install -y python3 build-essential
RUN mkdir -p /workspace/node_modules
COPY ["./dist", "./package.json", "/workspace/"]
WORKDIR /workspace
RUN npm install --production --save-exact
COPY ["./node_modules", "/workspace/node_modules/"]
EXPOSE 3000
CMD npm start
