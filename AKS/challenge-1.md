Details for Challenge:
ACR Login Server: registryhnj9475.azurecr.io
ACR Username: registryhnj9475
ACR Password: RxySg/ePKEd+9Whyy=JzYk9WXfYcir4/
SQL Server: sqlserverhnj9475
SQL Server Username: sqladminhNj9475
SQL Server Password: gE7nx9Bz2
Simulator url: simulatorregistryhnj9475.ukwest.azurecontainer.io
api-dev password: yB9pw7Hp2
web-dev password: fF8il1So4

hacker2gvv@msftopenhack7017ops.onmicrosoft.com
YS$$)q7s

Username = Hacker
password = Password123!

docker build -f Dockerfile -t "tripinsights/trips:1.0"

docker build -f C:\Users\hacker\OG010\containers_artifacts-1\dockerfiles\Dockerfile_4 -t "tripinsights/trips:1.0" .

docker run -d -p 8080:80 --name trips -e "SQL_PASSWORD=$SQL_PASSWORD" -e "SQL_SERVER=$SQL_SERVER" -e "OPENAPI_DOCS_URI=http://$EXTERNAL_IP" tripinsights/trips:1.0

docker build -f Dockerfile -t "tripinsights/trips:1.0"
Dockerfile_4

ACR Username: registryhnj9475
ACR Password: RxySg/ePKEd+9Whyy=JzYk9WXfYcir4/

SQL:
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=strongpass!55464" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest

DB:
mydrivingDB
username=sa
password=strongpass!55464

DataLoad:
docker run --network bridge -e SQLFQDN=10.0.0.6 -e SQLUSER=sa -e SQLPASS=strongpass!55464 -e SQLDB=mydrivingDB registryhnj9475.azurecr.io/dataload:1.0

Application:
PS C:\Users\hacker\OG010\containers_artifacts-1> docker run -d -p 8080:80 --name trips -e "SQL_PASSWORD=strongpass!55464" -e "SQL_SERVER=10.0.0.6" -e "OPENAPI_DOCS_URI=http://52.147.207.176" -e "SQL_USER=sa" -e "SQL_DBNAME=mydrivingDB" tripinsights/trips:1.0

Once all tested, push the image to ACR
docker tag tripinsights/trips:1.0 registryhnj9475.azurecr.io/tripinsights/trips:1.0
docker push registryhnj9475.azurecr.io/tripinsights/trips:1.0


docker build . -t "tripinsights/user-java:1.0"
docker tag tripinsights/user-java:1.0 registryhnj9475.azurecr.io/tripinsights/user-java:1.0
docker push registryhnj9475.azurecr.io/tripinsights/user-java:1.0