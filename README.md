# MySql Dump plugin  for Dokku

Save and load mysql dump
##Install

    cd /var/lib/dokku/plugins
    git clone https://github.com/nea88/dokku_mysql_dump-plugin
    dokku plugins-install

##Commands

    $ dokku help
    mysql_dump:info <app>       Display database dumps informations
    mysql_dump:save_dump <db> Save dump from container to default path
    mysql_dump:load_dump <db> <filename> Load dump to container
    mysql_dump:save_to_path <db> <path> Save dump to path
    mysql_dump:load_all Load all dumps from default path
    mysql_dump:save_all Save all dumps to default path
    mysql_dump:get_dump_from_url <app> <user> <password> <host> <port>
    mysql_dump:clear_db <db>    drop all tables from custom db

##Simple usage


Create a new DB:

    $ mysql_dump:save_dump bla            # Server side
    $ ssh dokku@server mysql_dump:save_dump bla # Client side

----> Saving bla sql dump
-----> Database dump saved


##Advanced usage

mysql_dump:save_to_path bla /home/dokku/bla.sql
----> Saving bla sql dump
-----> Database dump saved

##Dependences
mysql
mysqldump
https://github.com/Nea88/dokku_mysql_wp_plugin.git

##Thanks
* [hughfletcher/dokku-mysql-plugin](https://github.com/hughfletcher/dokku-mysql-plugin)
