# PostgreSQL + PgAdmin4 on ECS Local Network

This docker-compose was created to help local development firing up the latest PostgreSQL image and
PgAdmin4 and ecs-local-network. It was based on [this](https://github.com/mrts/docker-postgresql-multiple-databases) repository and changed for my needs.

## Usage

### Env

Rename the file `.env-example` to `.env` and change the values for your case.

### Fire up
To build and run the image just execute:
```bash
docker-compose up
```
If you want to run them in background just add the --detach flag
```bash
docker-compose up -d
```

### ECS Local Network (Or other network)

If you don't have ecs-local-network you can create by using the following command:
```bash
docker network create ecs-local-network
```

Or you can change the docker-compose file to use you own network driver
```yml
...
networks:
      ecs-local-network: null
...
networks:
  ecs-local-network:
    external: true
```