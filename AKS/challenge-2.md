SQL Server: sqlserverhnj9475
SQL Server Username: sqladminhNj9475
SQL Server Password: gE7nx9Bz2

kubectl create secret generic sqlaccess --from-literal=sqluser="sqladminhNj9475" --from-literal=sqlpass="gE7nx9Bz2" --from-literal=sqlserver="sqlserverhnj9475"

docker run -d -p 8080:80 --name poi -e "SQL_USER=sa" -e "SQL_PASSWORD=gE7nx9Bz2" -e "SQL_SERVER=10.0.0.5" -e "SQL_DBNAME=mydrivingDB" -e "ASPNETCORE_ENVIRONMENT=Local" tripinsights/poi:1.0