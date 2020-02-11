## Profiles REST API

Learning and understanding Python Django Framework.

## Steps to using docker and django
- Create a directory for the project
- Change to the created directory and add a Dockerfile as see
- Create a ```requirements.txt``` file with dependencies necessary
- Create a ```docker-compose.yml``` file.Mount a volume in which Django will create all the required files (Created ```src``` in this case)
- Run ```docker-compose build [service-name]``` to build an image from a docker-compose service
- Run a command on a container of the service using Django Admin:

```
docker-compose run [service-name] django-admin.py startproject [app-name] .
```
This creates necessary files in the container which are automatically mounted to our ``src`` directory including ```manage.py``` (Refer to the command in `docker-compose.yml` for the `profiles` service)

- Then create an app like:

```
docker-compose run [service_name] python manage.py startapp [app_name]
```

- Boot the docker-compose network up by running:

```
docker-compose up -d --build
```