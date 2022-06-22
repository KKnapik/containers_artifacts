kubectl create secret generic sqlaccess --from-literal=sqluser="sqladminhNj9475" --from-literal=sqlpass="gE7nx9Bz2" --from-literal=sqlserver="sqlserverhnj9475.database.windows.net"

docker run -d -p 8080:80 --name poi -e "SQL_USER=sa" -e "SQL_PASSWORD=gE7nx9Bz2" -e "SQL_SERVER=10.0.0.5" -e "SQL_DBNAME=mydrivingDB" -e "ASPNETCORE_ENVIRONMENT=Local" tripinsights/poi:1.0

to create a service from yaml definition, use following command:
kubectl create -f user-java.yml
kubectl apply -f user-java.yml

LOGIN TO CLUSTER
az aks get-credentials --resource-group aks-challenge-3 --name aks-challenge-3 --admin