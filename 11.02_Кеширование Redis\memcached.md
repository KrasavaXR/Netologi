# Домашнее задание к занятию «Кеширование Redis/memcached - Деев Валерий»

---

### Задание 1. Кеширование 

Приведите примеры проблем, которые может решить кеширование.

- Повышение производительности
- Увеличение скорости ответа
- Оптимизация нагрузки на базы данных
- Сглаживание бустов трафика

---

### Задание 2. Memcached

Установите и запустите memcached.

*Приведите скриншот systemctl status memcached, где будет видно, что memcached запущен.*
  ![image](https://github.com/KrasavaXR/Netologi/blob/74ddf052e2cb3895808704c70bdd9e2674682f42/2.jpg)

---

### Задание 3. Удаление по TTL в Memcached

Запишите в memcached несколько ключей с любыми именами и значениями, для которых выставлен TTL 5. 

*Приведите скриншот, на котором видно, что спустя 5 секунд ключи удалились из базы.*

- **Скрипт для выполнения задания на Python 3**
```
from pymemcache.client import base
import time

db = base.Client(('localhost', 11211))

db.set('kl1', '100', 5)
db.set('kl2', '200', 5)
db.set('kl3', '300', 5)

print("kl1 - ", db.get('kl1'))
print("kl2 - ", db.get('kl2'))
print("kl3 - ", db.get('kl3'))

print("   Ожидание 5 секунд...")
time.sleep(5)

print("kl1 - ", db.get('kl1'))
print("kl2 - ", db.get('kl2'))
print("kl3 - ", db.get('kl3'))
```
  ![image](https://github.com/KrasavaXR/Netologi/blob/74ddf052e2cb3895808704c70bdd9e2674682f42/3.jpg)

---

### Задание 4. Запись данных в Redis

Запишите в Redis несколько ключей с любыми именами и значениями. 

*Через redis-cli достаньте все записанные ключи и значения из базы, приведите скриншот этой операции.*
  ![image](https://github.com/KrasavaXR/Netologi/blob/74ddf052e2cb3895808704c70bdd9e2674682f42/4.jpg)
