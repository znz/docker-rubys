# docker-rubys

docker image with all maintained ruby releases.

## Usage

### Trusted Builds

    docker pull znzj/docker-rubys

### Local Build

    docker build -t znzj/docker-rubys rubys

### Run

    docker run -i -t znzj/ruby-rubys

In docker:

    rbenv each ruby -v
