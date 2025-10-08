## 1. Загрузите образ node версии 15.14
docker pull node:15.14<br>

15.14: Pulling from library/node
7b6173a10eb8: Pull complete
55fab5cadd3c: Pull complete
6041b69671c6: Pull complete
989c5d2d2313: Pull complete
4b57d41e8391: Pull complete
bd821d20ef8c: Pull complete
dc05be471d51: Pull complete
bfde2ec33fbc: Pull complete
787f5e2f1047: Pull complete
Digest: sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627
Status: Downloaded newer image for node:15.14
docker.io/library/node:15.14

---

## 2. Запустите контейнер node в интерактивном режиме подключения терминала, поименуйте его mynode, передайте две переменные среды NAME=<ваше имя> и SURNAME=<ваша фамилия>

docker run -it --name mynode -e NAME=ВашеИмя -e SURNAME=ВашаФамилия node:15.14<br>

node:15.14<br>
Welcome to Node.js v15.14.0.<br>
Type ".help" for more information.<br>

---

## 3. В интерактивной среде выполнения node выполните скрипт, который выведет на экран приветствие: Привет, <ваше имя> <ваша фамилия>!, эти данные должны быть получены из переменных среды
console.log(`Привет, ${process.env.NAME} ${process.env.SURNAME}!`);<br>
Привет, ВашеИмя ВашаФамилия!<br>

---

## 4. Остановите контейнер
docker stop mynode<br>
mynode<br>

---

## 5. Удалите образ node версии 15.14
docker stop 2d2179902a31<br>
docker rm 2d2179902a31<br>
docker rmi -f node:15.14<br>

Untagged: node:15.14<br>
Deleted: sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627<br>