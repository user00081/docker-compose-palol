# Luca Palo DEVELOPER exercise

### Dependencies for deploying on local environment
- Install Docker Community Edition: https://docs.docker.com/install/
- Install Docker Compose: https://docs.docker.com/compose/install/
- Install git git-cli: if you are on Windows https://git-scm.com/download/win if in nix use your package manager to install git and git-cli packages

### Deployment on local environment
- Clone repository
- cd in cloned folder
- Run `docker-compose up`
- Webserver is reachable from http://localhost:8080

### Credits
https://github.com/doctrine/doctrine2-orm-tutorial

### TODO
- Fix php-fpm volume.
- Fix IP in httpd.
- Add image, as link.
- Add upload functionality.
- Add many to many relation between Product and tag.
- Implement method for updating and inserting images and tags.
