# Self-Host Repository

## Requirements
- Docker version LTS
- Docker-compose version 3.7+

## Usage

*Note: we recommend to set executable permissions to ttriage-cli by running `chmod +x ttriage-cli`. *

Install on a new Server
----------
1. Edit the file `config-front.yml` and `docker-compose.yml` to set customized configuration like ports, database usage, etc.
2. Edit the configuration file `ttriage.conf` and set all the configuration constants with your personal values.
3. Execute `./ttriagle-cli pull` or `./ttriagle-cli import` to install/import a ttriage image. Do a `./ttriage-cli pull --help` for more information.
4. Execute `./ttriagle-cli pull <backend-hash> <frontend-hash>` to pull specific backend and frontend images in the command line. 
   * Example: `./ttriagle-cli pull 7a52981547df2eb9bbb016f4cc3410aad1698357 a585fa538f7046767cf3abeca3da3b8e0f430b14`

Upgrading to newer images versions.
----------
Usage: `./ttriagle-cli upgrade <backend|frontend> <image-hash>`
Upgrade and recreate a single container [backend|frontend]
Example: `./ttriagle-cli upgrade frontend a585fa538f7046767cf3abeca3da3b8e0f430b14`

Alternative you can upgrade both images with `./ttriagle-cli upgrade all <backend-image-hash> <frontend-image-hash>`
Example: `./ttriagle-cli upgrade all 7a52981547df2eb9bbb016f4cc3410aad1698357 a585fa538f7046767cf3abeca3da3b8e0f430b14`

Upgrade to image tagged as 'latest'
$0 upgrade <backend|frontend|all>
Upgrades backend, frontend or both respectively using tag 'latest' as default
Example: `./ttriagle-cli upgrade all`

Rebuild a container
----------
Usage: `./ttriagle-cli rebuild <backend|frontend|all>`
It will recreate one or all containers with the same image. This is useful to hard reset a container.
Example: `./ttriagle-cli rebuild backend`
Example: `./ttriagle-cli rebuild all`

Useful
----------
This command `docker logs -f <backend_container_id>` allows to watch the backend logs in real time
