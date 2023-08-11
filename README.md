# wordpress-docker-traefik
Wordpress set up with docker compose and traefik proxy.

## Requirements

A server running docker compose. The resource settings are optimized for a server with 4GB of RAM and a 4 core CPU.

## Setup

1. Clone this repo to your machine.

    ```
    git clone https://github.com/linobino1/wordpress-docker-traefik.git
    ```

1. create `.env` file from `.env.example`
    
    ```
    cp .env.example .env
    ```
    
1. Edit `.env` file and set your own values.
    - `DOMAIN`: your domain name
    - `MYSQL_ROOT_PASSWORD`: a password for the mysql root user
    - `MYSQL_PASSWORD`: a password for the mysql user `wp`
    - `BACKEND_AUTH`: authentication string for phpmyadmin and the traefik dashboard.
        Generate one with `htpasswd -nb <user> password`.  
        Replace all `$` with `$$` in the generated string.  
    
1. Start the containers
    
    ```
    docker-compose up -d
    ```

