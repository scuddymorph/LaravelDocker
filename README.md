# LaravelDocker

preferences: installed apps: composer

clone the repo
go into the folder where docker-compose.yml is located
run: composer create-project laravel/laravel myapp
change the workdir in the docker-compose.yaml and dockerfile in to laravel workdir (myapp)
run: docker-compose up -d
After building the docker containers there is maybe an error message in case of permission:

login into the docker with ssh: 
                                    docker exec -it <container name> /bin/bash

start the script:
                                    root@goodbytes:/app# php artisan storage:link

change the owner of the project:         

                                    root@goodbytes:/app# chown -R www-data:www-data ./bootstrap/
                                    root@goodbytes:/app# chown -R www-data:www-data ./public/   
                                    root@goodbytes:/app# chown -R www-data:www-data ./storage/
        NOW it should work !!!

maybe you have to change the right permission:

                                    root@goodbytes:/app# chmod 775 -R ./public/
                                    root@goodbytes:/app# chmod 775 -R ./bootstrap/



