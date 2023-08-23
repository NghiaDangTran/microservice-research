# what is jenkins
 - it is an automation tools for any task
# Build types
 - freestyle Build
     - simplest method to create a build
     - `feels` like shell scrtipting
 - pipelines: use grovey languate
docker run \
  --name jenkins-docker \
  --rm \
  --detach \
  --privileged \
  --network jenkins \
  --network-alias docker \
  --env DOCKER_TLS_CERTDIR=/certs \
  --volume jenkins-docker-certs:/certs/client \
  --volume jenkins-data:/var/jenkins_home \
  --publish 8080:8080 \
  docker:dind \
  --storage-driver overlay2
 - 
