# Alembic installation
## Steps
### 1. Installation
>`$ pip install alembic`

### 2. Initialization
It will create a directory named 'alembic' inside current directory  
>`$ cd /home/saiful/Projects/myapp/myapp`  
>`$ alembic init alembic`

### 3. Edit config files
##### Edit alembic.ini like below  
>prepend_sys_path = ..  
>sqlalchemy.url = sqlite:///./simple_erp.db (if sqlite database)

##### Edit env.py like below  
>from myapp.sql_models import Base  
>target_metadata = Base.metadata

### 4. Autogenerate revision
##### It will create revision in the "alembic/version" folder, check to see whether it is corrctly reflecting changes  
>`$ alembic revision --autogenerate -m "Add all tables"`

### 5. Running migration
##### This is will create/drop/modify tables/columns etc in the database  
>`$ alembic upgrade head`  

### 6. Check logs 
>`$ alembic history --verbose` 
>>Rev: a5b3be35c1ca (head)  
>>Parent: <base>  
>>Path: /home/saiful/Projects/sserpapi/sserpapi/alembic/versions/a5b3be35c1ca_add_all_tables.py   
>><br/>
>>Add all tables 
>><br/>   
>>Revision ID: a5b3be35c1ca   
>>Revises:     
>>Create Date: 2023-10-02 12:59:46.209011  
><br/>

>`$ alembic current`
>>INFO  [alembic.runtime.migration] Context impl SQLiteImpl.  
>>INFO  [alembic.runtime.migration] Will assume non-transactional DDL.  
>>a5b3be35c1ca (head)  
><br/> 
  
<br/>

#### For details https://alembic.sqlalchemy.org/en/latest/index.html#