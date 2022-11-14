# Create an query to  get all the table name and row count of DB
<b> In MYSQL:</b>

```
SELECT table_name, table_rows FROM information_schema.tables
WHERE table_schema = 'older_user'; 
```
<b> In Django:</b>

```python
from django.db import connection

cursor = connection.cursor()
data_dict = dict()
cursor.execute('SELECT table_name, table_rows FROM information_schema.tables WHERE table_schema = "older_user"')
data = cursor.fetchall()
for item in data:
    data_dict[item[0]] = item[1]
```


