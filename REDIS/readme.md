### Установка 
1. Запукаем 
```sh 
  docker-compose up -d  
```
2. Открываем в [браузере](http://localhost:8081)
3. Для остановки и удаления
```sh 
  docker-compose down -v  
```


### Что такое REDIS? []
_Сервер структуры данных который хранится в памяти. Ключ => Значение_

#### Типы
* Строка (String)
* Битовый массив (Bitmap)
* Битовое поле (Bitfield)
* Хеш-таблица (Hash)
* Список (List)
* Множество (Set)
* Упорядоченное множество (Sorted set)
* Геопространственные данные (Geospatial)
* Структура HyperLogLog (HyperLogLog)
* Поток (Stream)