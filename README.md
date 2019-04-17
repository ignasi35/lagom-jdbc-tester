# Lagom JDBC tester

To run with SQL Server use:

```
$ docker run -e 'ACCEPT_EULA=Y' \
             -e 'SA_PASSWORD=YourStrongPassw0rd..'    \
             -p 1433:1433 \
             --name TestDB \
             -d mcr.microsoft.com/mssql/server:2017-latest
```

Then, use the [VSCode instructions for SQL Server](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-develop-use-vscode?view=sql-server-2017) to create a `TestDB` database:

```
-- comment
-- Create a new database called 'TestDB'
-- Connect to the 'master' database to run this snippet
USE master
GO
-- Create the new database if it does not exist already
IF NOT EXISTS (
    SELECT name
        FROM sys.databases
        WHERE name = N'TestDB'
)
CREATE DATABASE TestDB
GO
```
