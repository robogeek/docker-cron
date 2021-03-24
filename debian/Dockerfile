FROM debian:jessie

# Install cron, certbot, bash, plus any other dependencies
# (1) install cron
RUN apt-get update && apt-get install -y cron bash wget

# (2) Set up a crontab entry
# This installs a Crontab entry which
# runs "certbot renew" on the 2nd and 7th day of each week at 03:22 AM
#
# cron(8) says the Debian cron daemon reads the files in /etc/cron.d,
# merging into the data from /etc/crontab, to use as the system-wide cron jobs
#
# RUN echo "22 03 * * 2,7 root /scripts/certbot-auto renew" >/etc/cron.d/certbot

# (3) Start cron in the foreground
CMD [ "cron", "-f" ]