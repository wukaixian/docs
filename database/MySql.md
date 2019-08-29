## data type

| data type                 | description                   |
| ------------------------- | ----------------------------- |
| int [unsigned]            | 4 byte                        |
| tinyint [unsigned]        | 2 byte                        |
| decimal(18,2)  [unsigned] | 4 byte                        |
| varchar(20)               | variable length,up to 65,535  |
| year                      | range 1901 to 2155, and 0000. |
| date                      | yyyy-MM-dd                    |
| datetime                  | YYYY-MM-DD hh:mm:ss           |

## create syntax

* **database**

  ```mysql
  create database if not exists db_name
  ```

* **table**

  ```mysql
  create table if not exists table_name(
      id int unsigned not null row_increment,
      username varchar(20) not null comment('comment'),
      create_time datetime not null,
      is_delete tinyint not null check(is_delete in(0,1),
      update_time datetime not null,
      primary key(id)                                
  ) comment('table comment')
  ```

  

## drop syntax

* **database**

  ```mysql
  drop database if exists db_name
  ```

* **table**

  ```mysql
  drop table if exists tb_name
  ```

  