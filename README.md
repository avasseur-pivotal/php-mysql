# Overview

This simple PHP application demonstrates how to connect to a MySQL service on Pivotal Cloud Foundry. This application allows the user to create a new table, and enter records into the database using the UI.

# Deployment

You need to create an instance of MySQL in your space named _php-mysql-db_

Refer to the _manifest.yml_ for details, or if you need to change default route or application name.

On Pivotal Cloud Foundry, using Pivotal MySQL service you can use:
```
cf create-service p-mysql 100mb php-mysql-db

cf push
```

# Session in Redis

The application can also demonstrate Redis backend for PHP session with buildpack activated service.
```
# service name must contain redis-sessions
cf create-service p-redis shared-vm redis-sessions-demo
```

# Note on working offline (private platform offline with no internet access)

The PHP buildpack can activate and download dependencies from the internet but on offline private platform this is not possible.

The application has thus a `.bp-config/` to explicitly activate PHP dependencies that are used by the application.
These dependencies are included in the buildpack release but are only staged into the container if they are needed.

(refer to the php buildpack docs for more details)
https://docs.cloudfoundry.org/buildpacks/php/gsg-php-config.html


## Credits

Forked from https://github.com/IBM-Bluemix/php-mysql
The Bluemix version relies on proprietary Bluemix manifest.yml extensions _declared-services_ and does not have correct offline behavior

