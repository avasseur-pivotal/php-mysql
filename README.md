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



## Credits

Forked from https://github.com/IBM-Bluemix/php-mysql
The Bluemix version relies on proprietary Bluemix manifest.yml extensions _declared-services_

