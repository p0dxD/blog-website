FROM node:11.13.0-alpine

# create destination directory
RUN mkdir -p /usr/src/nuxt-app
WORKDIR /usr/src/nuxt-app

# copy the app, note .dockerignore
COPY . /usr/src/nuxt-app/

RUN ls -la /usr/src/nuxt-app/
# expose 5000 on container
EXPOSE 8082

# set app serving to permissive / assigned
ENV NUXT_HOST=0.0.0.0
# set app port
ENV NUXT_PORT=8082

# start the app
CMD [ "npm", "start" ]
