az acr login --name {acrName}
docker tag nginx {acrName}.azurecr.io/{container}:{tag}
