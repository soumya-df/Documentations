# Data Façade PostgreSQL Integration

# Prerequisite before connecting

Many data sources are behind firewalls that require Data Facadé’s IP addresses to be allowed to connect. Depending on your infrastructure, this often means editing your firewall configuration.

## IP address to be whitelisted

1. [**3.128.121.148**](https://us-east-2.console.aws.amazon.com/vpc/home?region=us-east-2#ElasticIpDetails:AllocationId=eipalloc-00fdfb9ae48a48da8)
2. [**3.133.225.21**](https://us-east-2.console.aws.amazon.com/vpc/home?region=us-east-2#ElasticIpDetails:AllocationId=eipalloc-019695dce49261946)
3. [**3.19.125.171**](https://us-east-2.console.aws.amazon.com/vpc/home?region=us-east-2#ElasticIpDetails:AllocationId=eipalloc-05162d0403cac8a43)

## Grants required for connection (following the principle of least privilege)

```sql
GRANT CONNECT ON DATABASE "defaultdb" TO "datafacade";
GRANT CREATE ON DATABASE "defaultdb" TO "datafacade";

GRANT USAGE ON SCHEMA public TO "datafacade";
GRANT SELECT ON ALL TABLES IN SCHEMA public TO "datafacade";

CREATE SCHEMA IF NOT EXISTS "datafacade_output";
GRANT ALL PRIVILEGES ON SCHEMA "datafacade_output" TO "datafacade";
GRANT ALL ON ALL TABLES IN SCHEMA "datafacade_output" TO "datafacade";

CREATE SCHEMA IF NOT EXISTS "datafacade_tmp";
GRANT ALL ON SCHEMA "datafacade_tmp" TO "datafacade";
GRANT ALL ON ALL TABLES IN SCHEMA "datafacade_tmp" TO "datafacade";
```

# Connecting using Data Facadé

To connect to PostgreSQL server, use the Data option on the left navigation pane and please follow the steps 

**Step 1**: Click Add Data Source.  and select  PostgreSQL from the list and click Connect.

![Untitled](Data%20Fac%CC%A7ade%20PostgreSQL%20Integration%209c1151cb7b154551bad694edf2df5910/Untitled.png)

![Untitled](Data%20Fac%CC%A7ade%20PostgreSQL%20Integration%209c1151cb7b154551bad694edf2df5910/Untitled%201.png)

The connection requires the following parameters:

1. **Instance name:** User defined name of the instance which will be shown in the Data Connections once the configuration if successful.
2. **SSL Mode:** PostgreSQL has 5 SSL modes: disable, allow, prefer, require, and verify-ca/verify-full. The latter modes verify client SSL certificates; verify-full also checks the certificate's hostname.
3. **Host:** IP Address of the Postgres Server . Examples: 110.232.214.121,[aws-postgres.us-east-2.com](http://aws-postgres.us-east-2.com/)
4. **Port:** Port on which the Postgres Server is listening for connections. Examples: 5432,8090.
5. **Database:** Name of the Database to connect to Examples: postgres,stage,production
6. **Username**: Name of the User which Data Facade will use for its operations
7. **Password**: Password for the given user

**Step 2**: Click “**Select Schemas”** once all the parameters are filled.

![Untitled](Data%20Fac%CC%A7ade%20PostgreSQL%20Integration%209c1151cb7b154551bad694edf2df5910/Untitled%202.png)

**Step 3**: Select the schemas under “**Schemas**” section and click on “**Configure Sync**”.

![Untitled](Data%20Fac%CC%A7ade%20PostgreSQL%20Integration%209c1151cb7b154551bad694edf2df5910/Untitled%203.png)

**Step 4**: Click on “**Sync Now**” to create the connection. 

💡You can also enable the “**Sync Schedule**”  button to sync your data warehouse periodically.

💡 You can set you data connection as default provider be checking the box on the left side of “**Make Default Provider**”.

![Untitled](Data%20Fac%CC%A7ade%20PostgreSQL%20Integration%209c1151cb7b154551bad694edf2df5910/Untitled%204.png)