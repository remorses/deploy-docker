# deploy-docker
deploy easily from ci tools to docker private registries

## Usage with circle-ci
```yaml
version: 2
jobs:
    deploy:
        docker:
           - image: xmorse/deploy-dockerhub
        environment:
             IMAGE_NAME: myimage
             REGISTRY: myregistry.com
        steps:
             - setup_remote_docker
             - checkout
             - run: USERNAME=$DOCKER_USERNAME PASSWORD=$DOCKER_PASSWORD /deploy
```

