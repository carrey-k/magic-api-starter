# Magic API Starter

### Start MySQL

With config file
```
docker run -p 3306:3306 --name mysql-name -v /my/custom.cnf:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=your-secret-pw -d mysql:latest
```

Without config file
```
docker run p 3306:3306 --name mysql-name -e MYSQL_ROOT_PASSWORD=your-secret-pw -d mysql:latest
```
