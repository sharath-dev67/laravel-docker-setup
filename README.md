# Laravel Docker
A simplified docker-compose workflow that sets up a network of containers for local Laravel development. 

## Usage

To start, make sure you have docker installed on your system, which can be found [https://docs.docker.com/compose/install/] and then clone this repository.

Create two new directories
- src
- mysql

Add the entire Laravel project to the `src` folder, then open a terminal and from this cloned respository's root run `docker-compose up -d --build`.
Open up your browser of choice to [http://localhost:8080](http://localhost:8080) and you should see your Laravel app running as intended. 

**Your Laravel app needs to be in the src directory first before bringing the containers up, otherwise the artisan container will not build, as it's missing the appropriate file.** 

**New:** Three new containers have been added that handle Composer, NPM, and Artisan commands without having to have these platforms installed on your local computer.
Use the following command templates from your project root, modifiying them to fit your particular use case:

- `docker-compose run --rm composer update`
- `docker-compose run --rm npm run dev`
- `docker-compose run --rm artisan migrate` 
- `docker-compose run --rm artisan seed`

Containers created and their ports (if used) are as follows:

- **nginx** - `:8080`
- **mysql** - `:3306`
- **php** - `:9000`
- **npm**
- **composer**
- **artisan**
