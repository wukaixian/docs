## Comment

``` sql
--comment for table
comment on table TableName is 'xx';

--comment for column
comment on column TableName.ColumnName is 'xxx';
```

## Create Sequence

```sql
--sequence range is [min,max],increment step is 1,start by 1
CREATE SEQUENCE seq_name MINVALUE 1 MAXVALUE 1000000 INCREMENT BY 1 START WITH 1;
```

## Create Trigger

```sql
CREATE TRIGGER trigger_name BEFORE INSERT ON TableName  REFERENCING OLD AS "OLD" NEW AS "NEW" FOR EACH ROW 
BEGIN
 SELECT seq_name.nextval INTO :new.id  FROM dual;
END;
/
```

## Create Index

```sql
Create Index IX_Name on TableName(columnName,...);
```

