FROM node:11.13.0-alpine
RUN mkdir -p /usr/src/nuxt-app
WORKDIR /usr/src/nuxt-app
# copy the app, note .dockerignore
COPY . /usr/src/nuxt-app/

RUN ls -la /usr/src/nuxt-app/
# expose 5000 on container
EXPOSE 81

# set app serving to permissive / assigned
ENV NUXT_HOST=0.0.0.0
# set app port
ENV NUXT_PORT=81

# start the app
CMD  echo $PUBLIC_KEY_SECRET | base64 -d > /usr/src/nuxt-app/public.pem \
&&  echo $PRIVATE_KEY_SECRET | base64 -d > /usr/src/nuxt-app/private.pem \
&& cat /usr/src/nuxt-app/private.pem \
&& cat /usr/src/nuxt-app/public.pem \
&& npm version \
&& ls -la \
&& npm start
