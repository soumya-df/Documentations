# Data Façade Snowflake Integration

This document provides instructions on how to integrate Data Facade with Snowflake by creating a dedicated Data Facade user and role, and granting the necessary privileges.

# Prerequisite before connecting

## ****Creating a Data Facade User and Role****

**Create a Data Facade User and Role:**

```sql
sqlCopy code
CREATE USER <DataFacade User> PASSWORD = <password>;
CREATE ROLE IF NOT EXISTS <DataFacade User Role>;
GRANT ROLE <DataFacade User Role> TO USER <DataFacade User>;

```

Replace `<DataFacade User>`with your preferred user name, `<password>` with your preferred password, and `<DataFacade User Role>` with your preferred role name.

## ****Granting Minimum Privileges****

**Grant Minimum Privileges:**

- Grant USAGE permission to the warehouse:
    
    ```sql
    GRANT USAGE ON WAREHOUSE <COMPUTE_WH> TO ROLE <DataFacade User Role>;
    ```
    
    Replace **`<COMPUTE_WH>`** with your warehouse name and **`<DataFacade User Role>`** with your preferred role name.
    
- Grant SELECT permission to the tables in the database:
    
    ```sql
    GRANT SELECT ON <tables that want to be accessed in DataFacade/ ALL TABLES> IN DATABASE <Database Name> TO ROLE <DataFacade User Role>;
    ```
    
    Replace **`<tables that want to be accessed in DataFacade/ ALL TABLES>`** with the tables you want to access or **`ALL TABLES`** if you want to access all tables. Replace **`<Database Name>`** with your database name and **`<DataFacade User Role>`** with your preferred role name.
    

- Grant USAGE permission to the database:
    
    ```sql
    GRANT USAGE ON DATABASE <Database Name> TO ROLE <DataFacade User Role>;
    ```
    
    Replace **`<Database Name>`** with your database name and **`<DataFacade User Role>`** with your preferred role name.
    
    ## ****Granting Schema Privileges****
    
    1. **Grant Schema Privileges:**
        - **Option 1:** If the customer grants privilege to create schema on the database:
            
            ```sql
            GRANT CREATE SCHEMA ON DATABASE <Database Name> TO ROLE <DataFacade User Role
            ```
            
            Replace **`<Database Name>`** with your database name and **`<DataFacade User Role>`** with your preferred role name.
            
        - **Option 2:** If the customer does not grant privilege to create schema on the database:
        The customer will have to create two schemas on the database: **`datafacade_tmp`** and **`datafacade_output`**. These schemas are used by DataFacade to store temporary results. Create **`datafacade_tmp`** and **`datafacade_output`** before executing the next SQL.
            - Grant `USAGE` permission on the schemas in the database:
                
                ```sql
                GRANT USAGE ON <schemas that want to be accessed in DataFacade/ ALL SCHEMAS> IN DATABASE <Database Name> TO ROLE <DataFacade User Role>;
                ```
                
                Replace **`<schemas that want to be accessed in DataFacade/ ALL SCHEMAS>`** with the schemas you want to access or **`ALL SCHEMAS`** if you want to access all schemas. Replace **`<Database Name>`** with your database name and **`<DataFacade User Role>`** with your preferred role name.
                
            - Grant `CREATE TABLE` privilege on the **`datafacade_tmp`** schema:
                
                ```sql
                GRANT CREATE TABLE ON SCHEMA "datafacade_tmp" TO ROLE <DataFacade User Role>;
                ```
                
                Replace **`<DataFacade User Role>`** with your preferred role name.
                
            - Grant `SELECT` permission on all tables created on the **`datafacade_tmp`** schema:
                
                ```sql
                GRANT SELECT ON FUTURE TABLES IN SCHEMA "datafacade_tmp" TO ROLE <DataFacade User Role>;
                ```
                
                Replace **`<DataFacade User Role>`** with your preferred role name.
                
            - Grant `DROP` permission on all future tables created on the **`datafacade_output`** schema:
                
                ```sql
                GRANT DROP ON FUTURE TABLES IN SCHEMA "datafacade_output" TO ROLE <DataFacade User Role>;
                ```
                
                Replace **`<DataFacade User Role>`** with your preferred role name.
                
            - Grant `SELECT` permission on all future tables created on the **`datafacade_output`** schema:
                
                ```sql
                GRANT SELECT ON FUTURE TABLES IN SCHEMA "datafacade_output" TO ROLE <DataFacade User Role>;
                ```
                
                Replace **`<DataFacade User Role>`** with your preferred role name.
                
    
    ## **Granting Privileges for Writing Back to the Warehouse**
    
    1. **Grant Privileges for Writing Back to the Warehouse:**
        - Grant `CREATE SCHEMA` permission on the target database:
            
            ```sql
            GRANT CREATE SCHEMA ON DATABASE <DataFacade Database Name> TO ROLE <DataFacade User Role>;
            ```
            
            Replace **`<DataFacade Database Name>`** with your database name and **`<DataFacade User Role>`** with your preferred role name.
            
        - Grant permission to create & drop tables in **`datafacade_tmp`** and **`datafacade_output`**.
    
    ---
    
    Please execute the above SQL commands in your Snowflake environment to set up the integration with Data Façade.