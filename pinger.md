## 1. Загрузите образ busybox последней версии
docker run -it --rm busybox
docker ps

CONTAINER ID   IMAGE     COMMAND   CREATED          STATUS          PORTS     NAMES
d68ea5bb8450   busybox   "sh"      40 seconds ago   Up 40 seconds             reverent_rubin

---

## 2. Запустите новый контейнер busybox с командой ping сайта netology.ru, и количеством пингов 7, поименуйте контейнер pinger
docker run --name pinger busybox ping -c 7 netology.ru

PING netology.ru (51.250.51.8): 56 data bytes
64 bytes from 51.250.51.8: seq=0 ttl=63 time=15.766 ms
64 bytes from 51.250.51.8: seq=1 ttl=63 time=15.849 ms
64 bytes from 51.250.51.8: seq=2 ttl=63 time=16.104 ms
64 bytes from 51.250.51.8: seq=3 ttl=63 time=16.072 ms
64 bytes from 51.250.51.8: seq=4 ttl=63 time=16.024 ms
64 bytes from 51.250.51.8: seq=5 ttl=63 time=16.087 ms
64 bytes from 51.250.51.8: seq=6 ttl=63 time=16.085 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 15.766/15.998/16.104 ms

---

## 3. Выведите на список всех контейнеров - запущенных и остановленных
docker ps -a

CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS  
   NAMES
4d535bd0ba25   busybox   "ping -c 7 netology.…"   28 seconds ago       Exited (0) 21 seconds ago
   pinger
d68ea5bb8450   busybox   "sh"                     About a minute ago   Up About a minute

---

## 4. Выведите на экран логи контейнера с именем pinger
docker logs pinger

PING netology.ru (51.250.51.8): 56 data bytes
64 bytes from 51.250.51.8: seq=0 ttl=63 time=15.766 ms
64 bytes from 51.250.51.8: seq=1 ttl=63 time=15.849 ms
64 bytes from 51.250.51.8: seq=2 ttl=63 time=16.104 ms
64 bytes from 51.250.51.8: seq=3 ttl=63 time=16.072 ms
64 bytes from 51.250.51.8: seq=4 ttl=63 time=16.024 ms
64 bytes from 51.250.51.8: seq=5 ttl=63 time=16.087 ms
64 bytes from 51.250.51.8: seq=6 ttl=63 time=16.085 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 15.766/15.998/16.104 ms

---

## 5. Запустите второй раз контейнера с именем pinger
docker rm pinger
docker run --name pinger busybox ping -c 7 netology.ru

PING netology.ru (51.250.51.8): 56 data bytes
64 bytes from 51.250.51.8: seq=0 ttl=63 time=15.775 ms
64 bytes from 51.250.51.8: seq=1 ttl=63 time=15.833 ms
64 bytes from 51.250.51.8: seq=2 ttl=63 time=15.899 ms
64 bytes from 51.250.51.8: seq=3 ttl=63 time=15.986 ms
64 bytes from 51.250.51.8: seq=4 ttl=63 time=16.045 ms
64 bytes from 51.250.51.8: seq=5 ttl=63 time=16.060 ms
64 bytes from 51.250.51.8: seq=6 ttl=63 time=16.050 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 15.775/15.949/16.060 ms

---

## 8. Определите по логам общее количество запусков команды ping и какое общее количество отправленых запросов
3 - запуска
9 - отправленных запросов

---

## 9. Удалите контейнер с именем pinger
docker rm pinger
pinger

---

## 10. Удалите образ busybox
docker container prune
Untagged: busybox:latest
Deleted: sha256:d82f458899c9696cb26a7c02d5568f81c8c8223f8661bb2a7988b269c8b9051e

---
