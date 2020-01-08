# Docker Node.js Image with oneAgent embebed "Hello World" Example

Thi example provides an image with node.js Hello Word application, dockerized and with Dynatrace OneAgent embebed.
This will use Docker multi-stage image builds, so Docker version 17.05 or higher is needed.
See  [Dynatrace Documentation](https://www.dynatrace.com/support/help/technology-support/cloud-platforms/amazon-web-services/installation/deploy-oneagent-on-aws-fargate/#expand-1358docker-multi-stage-image-builds) for more details

## Setup

First, checkout this project locally and then follow these steps:

- Docker is needed to be installed on the host [Install Docker](https://docs.docker.com/installation/)
- Edit the `Dockerfile` to replace `<your_URL>` with your Dynatrace URL i.e.:`myenvironment.live.dynatrace.com`, `mycluster.dynatrace-managed.com/e/myenvironment`
- Log in to Docker with your Dynatrace environment ID as username and PaaS token as password.
   `docker login -u <environmentID> <your_URL>`
- Build the Docker image: `docker build -t hello-world .`
- Run the image `docker run -d -p 3000:80 hello-world`
- Access to the app running `http://$(docker-machine ip default):3000`

