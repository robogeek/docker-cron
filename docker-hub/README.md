This directory contains a `Dockerfile` and build scripts to maintain the `robogeek/crond` image on Docker Hub.

An article describing the thought process behind this image is at: https://techsparx.com/software-development/docker/damp/docker-cron.html.md

This image is built on Alpine Linux (tiny container) and is meant to be used for running the Busy Box `crond` to run a set of _cron jobs_.  Hence, the `CMD` instruction runs `crond`.

In addition this image contains these packages:  mysql-client less gzip rsync

Those packages are deemed to be useful in writing _cron jobs_ for running backup tasks.

An example of using this is in `../wordpress-backup`.  The idea is to mount into the container directories containing shell scripts that serve as cron jobs.  The directories must mount to:

* `/etc/periodic/15min` - for jobs running every 15 minutes
* `/etc/periodic/hourly` - for jobs running every hour
* `/etc/periodic/daily` - for jobs running every day
* `/etc/periodic/weekly` - for jobs running every week

An important point is that the shell scripts must not have a file extension like `.sh`, because those files will be silently ignored by the `run-parts` program.

