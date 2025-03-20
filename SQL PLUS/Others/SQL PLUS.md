**SQL*Plus** is a command-line tool provided by Oracle for interacting with Oracle databases. It allows users to execute SQL queries, run scripts, and manage database objects.

### **How to Use SQL*Plus**

#### **1. Open SQL*Plus**

- On **Windows**, open Command Prompt and type:
    
    ```sh
    sqlplus /nolog
    ```
    
- On **Linux/Mac**, open a terminal and type:
    
    ```sh
    sqlplus /nolog
    ```
    

#### **2. Connect to an Oracle Database**

- If using a local database:
    
    ```sh
    CONNECT username/password@localhost:1521/orcl
    ```
    
- If using a remote database:
    
    ```sh
    CONNECT username/password@remote_host:1521/service_name
    ```
    

#### **3. Run SQL Commands**

Example:

```sql
SELECT * FROM employees;
```

#### **4. Run SQL Scripts**

To execute an SQL script (`my_script.sql`):

```sh
@my_script.sql
```

#### **5. Exit SQL*Plus**

```sh
EXIT;
```

Do you need help with a specific SQL*Plus task?