=====================
#                   #
#    DOCKER START   #
#                   #
=====================

- Build docker
`docker-compose up -d --build`
- Open php bash
`docker exec -it { PHP_CONTAINER_NAME } bash`
- Create symfony project (remove public folder if not removed)
`composer create-project symfony/skeleton`
- Install doctrine
`composer require doctrine`
- Setup DB url in .env file
`docker-compose run --rm php bin/console doctrine:database:create`
- Might need to chmod -777 mysql directory (`chmod 777  ./mysql`)
- Install encore for compiling js / scss
`docker exec -it { PHP_CONTAINER_NAME } bash`
`composer require encore`
- Install npm dependencies
`docker-compose run --rm { NODE_SERVICE_NAME } yarn/npm install`