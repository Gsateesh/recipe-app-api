# recipe-app-api

1. Please install WSL in windows from windows app store
2. run the commands below,
    docker build .
    docker-compose build
    
3. To run lint ( flake8 ) on the project, we need to run the following command.
    docker-compose run --rm app sh -c "flake8"
4. To create a Django project in the docker, run the command below.
    docker-compose run --rm app sh -c "django-admin startproject app ."
5. To run project in docker run the command below.
    docker-compose up
    our app runs at "http://127.0.0.1:8000/"