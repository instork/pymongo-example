# pymongo-example

## Prerequisites

 - make conda environment
```bash
$ make env                  # create anaconda environment
$ conda activate <new_env>  # activate anaconda environment
$ make setup                # initial setup for the project
$ make add_notebook         # add jupyter notebook kernel
```

- install mongodb
    - https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition
- Auth
    - change to admin
        ```bash
        $ mongo # launch mongo shell
        $ use admin
        ```
    - make admin user: 
        ```bash
        $ use admin
        $ db.createUser({ user: "mongoadmin" , pwd: "mongoadmin", roles: ["userAdminAnyDatabase", "dbAdminAnyDatabase", "readWriteAnyDatabase"]})
        ```
    - list all user
        ```
        $ show users
        ```
    - enable auth: add below on `/etc/mongod.conf`
        ```
        #security:
        security:
            authorization: "enabled"
        ```
        then
        ```bash
        $ sudo service mongod restart
        ```
        - https://medium.com/mongoaudit/how-to-enable-authentication-on-mongodb-b9e8a924efac
        