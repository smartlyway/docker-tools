FROM node:7.8.0

RUN npm install -g @angular/cli
RUN npm install -g npm-check-updates

# Set default work directory
WORKDIR /var/www

EXPOSE 4200

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"
