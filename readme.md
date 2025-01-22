## docker-revproxy

I created this docker compose as an example of how to run two nginx containers behind a nginx reverse proxy container.

## Description:

 - **ns8-app1** is the first docker container with an example index.html on /var/www/app
 - **ns8-app2** is the second docker container, same as the first one, but with a different index.html for better understanding.
 - **revproxy** is the reverse proxy container that proxy passes to both app servers

## Usage:

You will have to create two entries on **/etc/hosts** to be able to test:

    127.0.0.1	app1.asd.gg
    127.0.0.1	app2.asd.gg

**Build the images:**
After cloning the git, jump into the folder where docker-compose.yml is and build the images

    docker compose build
Next create the containers

    docker compose up -d

To start and stop the containers just run

    docker compose stop
or

    docker compose start
If at any point you change the docker files you will need to build the images again.

    docker compose build

