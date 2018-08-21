# How to run a Microsoft SQL Server on macOS

For a specific project I needed a copy of the Microsoft SQL Server database on my local machine. Since I'm not running Windows I ended up using a docker container and import the SQL script on the command line with an open-source command line interface [sql-cli](https://www.npmjs.com/package/sql-cli)

1. Install and run Docker
2. Increase the memory in Preference to at least 4GB
3. Download the official [SQL Server for Linux](https://hub.docker.com/r/microsoft/mssql-server-linux/) with `docker pull microsoft/mssql-server-linux`
4. Launch the image `docker run -d --name docker_name -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=strong_password' -p 1433:1433 microsoft/mssql-server-linux`

Reference: [How to install SQL server on a Mac](https://database.guide/how-to-install-sql-server-on-a-mac/)

Importing a very large SQL with DBeaver didn't work that well, and I also think that not all features for SQL Server are supported, so 

5. Install sql-cli with `yarn global add sql-cli` (or with npm)
6. Go to the directory which contains the `.sql` script
6. Connect with `mssql -u sa -p strong_password` in that directory
7. Run `.run name_of_script.sql`




