FROM node:7.8.0

RUN npm install -g @angular/cli

ARG PUID=2000
ARG PGID=2000
RUN groupadd -g $PGID angular-cli && \
useradd -u $PUID -g angular-cli -m angular-cli

# Set default work directory
WORKDIR /var/www

CMD exec /bin/bash -c "trap : TERM INT; sleep infinity & wait"