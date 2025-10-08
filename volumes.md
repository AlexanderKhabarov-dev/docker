## 1 
docker pull node:15.14

15.14: Pulling from library/node
4b57d41e8391: Pull complete
dc05be471d51: Pull complete
bd821d20ef8c: Pull complete
787f5e2f1047: Pull complete
bfde2ec33fbc: Pull complete
7b6173a10eb8: Pull complete
989c5d2d2313: Pull complete
55fab5cadd3c: Pull complete
6041b69671c6: Pull complete
Digest: sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627
Status: Downloaded newer image for node:15.14
docker.io/library/node:15.14

---

## 2 
docker run -d --name first_node -v C:/Users/User/Desktop/netology/docker/data:/var/first/data node:15.14 tail -f /dev/null

d70f15a741319ccfe2972a98d06e39fe2a41fd0edfd0444add491cc0768fad2b

---

## 3
docker run -d --name second_node -v C:/Users/User/Desktop/netology/docker/data:/var/second/data node:15.14 tail -f /dev/null

7e609a3b1693aa56a66f3bb0e1a6697f711c123e30c2dd74821c15c224ced15e

---

## 4
docker exec -it first_node sh

---

## 5
echo "Содержимое файла от first_node" > /var/first/data/file_from_first.txt
echo "123" > /var/first/data/123.txt
exit

---

## 6
docker exec -it second_node sh

ls /var/second/data

cat /var/second/data/file_from_first.txt<br>
Содержимое файла от first_node

cat /var/second/data/123.txt<br>
123
exit

---

## 7 
docker stop first_node second_node<br>
first_node<br>
second_node

---

## 8
docker rm first_node second_node<br>
first_node<br>
second_node

---

## 9
docker rmi node:15.14

Untagged: node:15.14<br>
Deleted: sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627