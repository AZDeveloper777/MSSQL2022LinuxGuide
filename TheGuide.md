This guide assumes you already have Ubuntu 22.04 installed.  

1. Get the MS signing keys
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo tee /etc/apt/trusted.gpg.d/microsoft.asc
```
2. Tell Ubuntu to also use the MS Ubuntu SQL Server package repo
```
curl -fsSL https://packages.microsoft.com/config/ubuntu/22.04/mssql-server-2022.list | sudo tee /etc/apt/sources.list.d/mssql-server-2022.list
```
3. Install SQL Server
```
sudo apt-get update
sudo apt-get install -y mssql-server
```
4. Run MS SQL Server setup
```
sudo /opt/mssql/bin/mssql-conf setup
```
5. Verify that it is running correctly
```
systemctl status mssql-server --no-pager
```
6. Get the IP address of this machine
```
ip a
```
7. Test that you can connect with SSMS with the IP address from the previous step.
