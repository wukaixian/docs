- ### merge into

  ```sql
  merge into t [target table]
  using s [source table]
  on(t1.id=t2.id) [condition]
  when matched then delete
  [or]
  when matched then 
  	update t.name=s.name
  when not matched then insert;
  ```

- ### partition by （组内排序）

  ```sql
  select a.*,row_number() over(partition by groupid order by age) from table1 as a
  ```

  