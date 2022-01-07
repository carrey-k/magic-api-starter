# Step to Start

1. Install mysql
2. Create tables
```
create table test_data
(
    id   bigint       not null
            primary key,
                name varchar(100) null
                
);
INSERT INTO test_data (id, name) VALUES (1, 'magicApi');
INSERT INTO test_data (id, name) VALUES (2, 'xiaoDong');


CREATE TABLE `magic_api_file` (
  `file_path` varchar(512) NOT NULL,
    `file_content` mediumtext,
      PRIMARY KEY (`file_path`)
      
        ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4


CREATE TABLE `magic_api_backup` (
  `id` varchar(32) NOT NULL COMMENT '原对象ID',
    `create_date` bigint(13) NOT NULL COMMENT '备份时间',
      `tag` varchar(32) DEFAULT NULL COMMENT '标签',
        `type` varchar(32) DEFAULT NULL COMMENT '类型',
          `name` varchar(64) DEFAULT NULL COMMENT '原名称',
            `content` mediumtext COMMENT '备份内容',
              `create_by` varchar(64) DEFAULT NULL COMMENT '操作人',
                PRIMARY KEY (`id`,`create_date`)
                
        ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4

CREATE TABLE `user` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `username` varchar(255) COLLATE utf8_bin DEFAULT NULL,
  `password` varchar(255) COLLATE utf8_bin DEFAULT NULL,
  `addr` varchar(500) COLLATE utf8_bin DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
```

# Integrate with Swagger-UI
1. add below dependencies to pom.xml
```xml
<!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger2 -->
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger2</artifactId>
    <version>3.0.0</version>
</dependency>
<!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger-ui -->
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger-ui</artifactId>
    <version>3.0.0</version>
</dependency>
```

2. Download the latest Swagger-UI from its official repo
 `https://github.com/swagger-api/swagger-ui/releases` and copy all of files under `/dist` folder to your spring boot project folder `your_project/src/main/resources/static/swagger-ui`

3. Restart your project

4. Access `http://<localhost>:<server_port>/swagger-ui/index.html`


# Restore Examples
1. Start magic-api-starter at localhost
2. Open web URL in browser
3. Click the upload icon in the top right corner of header navigation bar
4. Choose the magic-api-example.zip
