# PHP Coverage report 


```bash
docker build -t  img-app . --force-rm
docker run -it --name app-cov --rm  -v "$(pwd):/app" img-app composer require --dev phpunit/phpunit
docker run -it --name app-cov --rm  -v "$(pwd):/app" img-app php vendor/bin/phpunit --coverage-html=coverage
```
