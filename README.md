# Postgres-Lec9-Jan-19-25
Prep for quiz
* PK= always unique and not null,not alway autoincrement
* DISTINCT: select distinct(country) -without duplicate= return set of countries
* INDEX - when using select by other property then id, 
it's better to improve performance, to create index for this property
  * when create property with UNIQUE, automatically index from this property
* primary key , must come with NOT NULL
* TEXT vs CHAR= in CHAR you can limit the length of string
* CURRENT_TIMESTEMP= can be a default in the column
* CHECK - a constraint function to check the value before insert/update : 
  * examples: CHECK(SALARY>0), CHECK(LENGTH(name)>4)
* FP - usually need NOT NULL 
  * attach on delete cascade constraint: 
  referenced to the fk on this table, but if you delete from the other table, the deleted to impact on this table too
  * if you delete on this table, it will not impact on the other table
* insert many: 
  * allways specify the column names insert into parent (col1,col2...) (val1,val2...)
  * ways:
    1) insert into parent (id,name) select id,name from prev_parent
    2) upsert: without raise id -insert into parent (id,name) values (3, 'danny' ) on conflict (id) do update set name='danny'
    3) insert into parent values (1,"n"),(2,"n"),(3,"n")
    4) replace - will insert the entire row with raise id