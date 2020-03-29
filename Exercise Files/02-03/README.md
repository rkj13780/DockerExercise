# Launch a Docker image

Find the Public IP for your Docker VM and login with:
ssh docker@{public_ip}

Connect to ACR
 - collect ACR name and password from the ACR "Access Keys" page

docker login {acr_name}.azurecr.io
user: {acr_user}
pass: {acr_pass}

Launch an instance:

docker run --rm --name -d -p 80:80 {acr_name}.azurecr.io/{container}:latest

Verify access:

curl localhost

