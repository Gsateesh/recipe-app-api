# recipe-app-api

1. Please install WSL in windows from windows app store
2. run the commands below,
    > docker build .
    > docker-compose build

3. To run lint ( flake8 ) on the project, we need to run the following command.
    > docker-compose run --rm app sh -c "flake8"
4. To create a Django project in the docker, run the command below.
    > docker-compose run --rm app sh -c "django-admin startproject app ."
5. To run project in docker run the command below.
    > docker-compose up
    our app runs at "http://127.0.0.1:8000/"
6. To test the application run command below.
    > docker-compose run --rm app sh -c "python manage.py test"

7. To make migrations we need to run command below
    > docker-compose run --rm app sh -c "python manage.py makemigrations"
8. To run migration do following
    First get the list of docker volume list by command below,
    > docker volume ls
    Then copy the respective volume name from terminal and run command below
    > docker-compose down
    > docker volume rm recipe-app-api_dev-db-data
    > docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py migrate"

9. Create a super user
    > docker-compose run --rm app sh -c "python manage.py createsuperuser"
        admin@example.com
        admin@123
