# Reset the MySQL DB Password

Stop the MySQL service  
Set the password to   
Restart the service  

  sudo /etc/init.d/mysql start
  sudo mysqld_safe --skip-grant-tables
  mysql -u root
  use mysql
  update user set password=password("123") where User="root"
  update user set authentication_string=password("123") where User="root"
  flush privileges
  quit
  sudo /etc/init.d/mysql stop

# Create a new user

  create user "abc" identified by "123";
  grant all privileges on *.* to "abc" with grant option;
  
# Plugin auth

If you can login with sudo mysql -u root but not with password, you likely have plugin authentication configured. Check the user table for the plugin column. Password authenticated users have the plugin column set to mysql_native_password whereas the plugin authenticated users have auth_socket instead.
