# Pass Environment Variables from Dokku to Docker Build Environment
For use with [dokku](https://github.com/progrium/dokku)

We found a need to export our dokku environment variables to a `.dokku.env`
file. This allows us to take the environment variables and use easily use them
in our `Dockerfile` with:

```bash
RUN if [ -f /<WORKDIR>/.dokku.env ]; then set -a && . /<WORKDIR>/.dokku.env; fi
```

## Installation
sudo dokku plugin:install https://github.com/ioutcomes/dokku-docker-env-variables-plugin

## Requirements
* Dokku version `0.4.5` or higher

## Usage
If you'd like to use a custom prefex for your .env file, you can set
`DOKKU_DOCKER_ENV_VAR_PREFIX` dokku environment variable to your prefix of
choice.

Your file will now be `.<DOKKU_DOCKER_ENV_VAR_PREFIX>.env`.

