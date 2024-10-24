__Запуск Docker__
```bash
docker compose up --build
```

__Установка Symfony__
1. Открыть docker image *php*
```bash
docker exec -it php bash  
```

2. Запустить
```bash
composer create-project symfony/skeleton:"6.2.*" .
```