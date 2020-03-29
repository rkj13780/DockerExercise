Build the image

docker build . -t hostname
docker tag hostname:latest hostname:v1

Run the image:

docker run --rm --name hostname -p 8080:80 -d hostname:v1

Test that the image works:

curl http://localhost:8080

Stop the running instance:

docker stop hostname

Clean up the local build/run environment:

docker rmi hostname:latest hostname:v1

