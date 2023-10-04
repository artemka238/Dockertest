# base image
FROM node:14.14.0

# set working directory
WORKDIR /app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# install and cache app dependencies
COPY package.json ./
RUN npm install
# RUN npm install @vue/cli@3.7.0 -g
# COPY ./vue_app .
# start app
CMD ["npm", "run", "serve"]

FROM nginx:1.21
RUN apt-get update \ 
    && apt-get install -y wget \
    && rm -rf /var/lib/apt/lists/*
RUN rm -rf /usr/share/nginx/html/*
# COPY --from=build /app/dist /app
