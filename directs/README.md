## These images are available as standard
------------------------------------------------

1> MYSQL:

    https://hub.docker.com/_/mysql
    version: 5.6

    $ docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag

    services:

  db:
    image: mysql
    # NOTE: use of "mysql_native_password" is not recommended: https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html#upgrade-caching-sha2-password
    # (this is just an example, not intended to be a production configuration)
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: example

  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080

    Using a custom MySQL configuration file
        The default configuration for MySQL can be found in /etc/mysql/my.cnf, which may !includedir additional directories such as /etc/mysql/conf.d or /etc/mysql/mysql.conf.d. 

        If /my/custom/config-file.cnf is the path and name of your custom configuration file, you can start your mysql container like this 

        $ docker run --name some-mysql -v /my/custom:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag

2> MEMCHACHED

    https://hub.docker.com/_/memcached
    version: 
    port: 11211


3> RABBITMQ

    https://hub.docker.com/_/rabbitmq
    version: 


4> TOMCAT

    https://hub.docker.com/_/tomcat
    version:
    