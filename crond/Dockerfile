ARG ALPINE_VER
# Use the official Alpine image as a base
FROM alpine:${ALPINE_VER}

# Install MySQL client and crond
RUN apk update && apk add mysql-client && apk add busybox-suid

# special configuration for mysql client - https://stackoverflow.com/a/78683658
COPY client.my.cnf /root/.my.cnf

# Copy your crontab file to the container
COPY cronjobs /etc/crontabs/root

# Start crond in the foreground
CMD ["crond", "-f"]