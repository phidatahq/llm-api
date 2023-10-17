## Api App

This repo contains the code for running a Api App in 2 environments:

1. `dev`: A development env running on docker
2. `prd`: A production env running on AWS ECS

## Setup Workspace

1. Create + activate a virtual env:

```sh
python3 -m venv ~/.venvs/llmenv
source ~/.venvs/llmenv/bin/activate
```

2. Install + init `phidata`:

```sh
pip install phidata
phi init -l
```

> from the `api-app` dir:

3. Setup workspace:

```sh
phi ws setup
```

4. Copy `workspace/example_secrets` to `workspace/secrets`:

```sh
cp -r workspace/example_secrets workspace/secrets
```

## Run FastApi App locally using docker

The [workspace/dev_resources.py](workspace/dev_resources.py) file contains the resources for the dev environment. Install [docker desktop](https://www.docker.com/products/docker-desktop) and run dev resources using:

```sh
phi ws up
```

Open [localhost:9090/docs](http://localhost:9090/docs) to view the FastApi docs.

### Shut down workspace

Shut down resources using:

```sh
phi ws down
```
