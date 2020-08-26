To run and build the container and collectstatic:

    docker-compose -f docker-compose.prod.yml up -d --build
    docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
    docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear


To Create a app in django:
    docker-compose up -d --build
    docker-compose exec web python manage.py startapp upload

To bring the containers down:
    docker-compose down -v
    docker-compose -f docker-compose.prod.yml down -v

To test prod:
    docker-compose -f docker-compose.prod.yml down -v
    docker-compose -f docker-compose.prod.yml up -d --build
    docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput