myproject-role
=========

This role deploy a application Myprojetc (https://github.com/reversondias/Myproject). The role prepar the server to receive the app.


Role Variables
--------------

There are variable on vars/main.yml:  

packages -> The requirements packges to run the app  
mariadb_root_password -> DB root password  
db_user -> User to connect on the data base application  
db_user_pass -> User password  
db_name -> The DB name to app
db_server -> The address of DB server


Example Playbook
----------------


     - name: Deploy Project App
       hosts: app
       roles:
        - myproject-role


Description
-----------

This role will install and cofigure a Database. You can use in the same server or another. Use the tag "database" for only install and configure a database server.  
After the DB server the role will deploy the app, after that its will configure a nginx server. The nginx is a proxy to app.  
It's possible configure only app and nginx using the tag "deploy_app".  

The application has a unit file that will up on boot. And the nginx use a template file, if necessary make some configuration it's can do by the template file.  
Database parameter are in a template too. If the necessary make some change use that.



