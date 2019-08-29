## create syntax

* **create database**

  ```mysql
  create database if not exists db_name
  ```

* **create table**

  ```mysql
  create table if not exists table_name(
      id int unsigned not null row_increment,
      username varchar(20) not null,
      create_time datetime not null,
      is_delete tinyint not null check(is_delete in(0,1),
      update_time datetime not null,
      primary key(id)                                
  )
  ```

  