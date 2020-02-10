FROM keymetrics/pm2:8-alpine

RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh tzdata shadow && \
    usermod --shell /bin/bash root

# Add global node packages
RUN npm i -g lsc

COPY motd /etc/motd

RUN chmod 0644 /etc/motd; echo '[ ! -z "$TERM" -a -r /etc/motd ] && cat /etc/motd' >> /etc/bash.bashrc

COPY usersessiontimout.sh /etc/profile.d/usersessiontimout.sh

RUN chmod +x /etc/profile.d/usersessiontimout.sh
