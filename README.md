# Домашнее задание к занятию 2 «`Кластеризация и балансировка нагрузки`» - Kadancev Vladimir

---

### Задание 1

- Запустите два simple python сервера на своей виртуальной машине на разных портах
- Установите и настройте HAProxy, воспользуйтесь материалами к лекции по [ссылке](2/)
- Настройте балансировку Round-robin на 4 уровне.
- На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy.

### Решение 1

[haproxy.cfg]()

`Cкриншот, где видно перенаправление запросов на разные серверы при обращении к HAProxy:`

![Скриншот](https://github.com/valdemar-2502/Clustering-and-load-balancing-Homework/blob/main/task%201%20haproxy.png)
![Скриншот](https://github.com/valdemar-2502/Clustering-and-load-balancing-Homework/blob/main/task%201%20haproxy2.png)

---

### Задание 2

- Запустите три simple python сервера на своей виртуальной машине на разных портах
- Настройте балансировку Weighted Round Robin на 7 уровне, чтобы первый сервер имел вес 2, второй - 3, а третий - 4
- HAproxy должен балансировать только тот http-трафик, который адресован домену example.local
- На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него.

### Решение 2

Добавляем домен `example.local` в `/etc/hosts` чтобы VM знала, какой IP соответствует доменному имени.

```
sudo nano /etc/hosts
```
добавляем строку (IP VM)
```
158.160.194.34  example.local
```

[haproxy.cfg]()

`Cкриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него:`

![Скриншот](https://github.com/valdemar-2502/Clustering-and-load-balancing-Homework/blob/main/task%202%20haproxy.png)
![Скриншот](https://github.com/valdemar-2502/Clustering-and-load-balancing-Homework/blob/main/task%202%20haproxy2.png)
