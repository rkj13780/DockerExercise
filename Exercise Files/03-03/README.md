# Test security groups
Log into the VM machine and run three containers:

ACR_NAME=liinacr
docker run --rm --name port80 -d -p 80:80 $ACR_NAME.azurecr.io/docker-azure:latest
docker run --rm --name port85 -d -p 85:80 $ACR_NAME.azurecr.io/docker-azure:latest
docker run --rm --name port90 -d -p 90:80 $ACR_NAME.azurecr.io/docker-azure:latest

curl localhost:90

From a remote machine:

curl {VM_IP}:80
curl {VM_IP}:90

Only the first should work remotely.
