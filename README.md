# Node.js Rest APIs with Express & MySQL example

## Project setup

`mysql` setup, install first:

```
sudo apt update
sudo apt upgrade
sudo apt install mysql-server
mysql --version # check installation
```

Start service and create table:

```
sudo service mysql start
sudo mysql -u root # no passwd by default
```

In mysql, set root password:

```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'SetRootPasswordHere';
exit
```

Then start secure installation:

```
sudo mysql_secure_installation
```

Now login to your database:

```
mysql -u root -p
```

Then create the database:

```
CREATE DATABASE rest_api_js;
USE rest_api_js;
CREATE TABLE IF NOT EXISTS `tutorials` (
  id int(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  title varchar(255) NOT NULL,
  description varchar(255),
  published BOOLEAN DEFAULT false
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
exit
```

Ensure that mysql is running:

```
sudo systemctl status mysql
```

Then install `node` packages:

```
sudo apt install npm
npm install
```

### Run

Now open `/app/config/db.config.js` and edit your password there:

```
module.exports = {
  HOST: "localhost",
  USER: "root",
  PASSWORD: "[YOUR_SQL_PASSWORD]",
  DB: "rest_api_js",
};
```

```
node server.js
```
