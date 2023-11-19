# File Overview
## Prerequisite 
- AWS CLI installed
- CLI configured with a user that has specific permissions(ECR and ECS)
- Create a repository(ECR)

### Docker file explanation
This docker file uses the Ubuntu 18.04 image.
The `RUN` instructions update the package cache, installs some software packages for the web server, and then writes the `Hello world` content to the web server document root.
- The `EXPOSE` instruction exposes port 80 on the container,
- `CMD` starts the web server

- Build the docker image from Dockerfile
`docker build -t dockerapacheserver .`
- Run `docker images` to verify that the image was created correctly.
`docker images --filter reference=dockerapacheserver`

- Run the newely built image
`docker run -t -i -p 80:80 dockerapacheserver`

- Open a browser and point to the server that is running Docker and hosting your container.
`http://localhost:80`

## Deploy to Elastic Container Registry
- Registry comes with configurations setups to configure both access, building your image, tag your image and pushing to the repository.

## Create ECS
- 