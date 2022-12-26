University: ITMO University
Faculty: FICT
Course: Network programming
Year: 2022/2023
Group: K34202
Author: Anisimova Rsenia
Lab: 4
Date of create: 15.12.2022
Date of finished: 24.12.2022

# Лабораторная работа №4 "Базовая 'коммутация' и туннелирование используя язык программирования P4"
### Описание
В данной лабораторной работе ознакомлены на практике с языком программирования P4, разработанный компанией Barefoot (ныне Intel) для организации процесса обработки сетевого трафика на скорости чипа. Barefoot разработал несколько FPGA чипов для обработки трафика которые были встроенны в некоторые модели коммутаторов Arista и Brocade.

### Цель работы
Изучить синтаксис языка программирования P4 и выполнить 2 задания обучающих задания от Open network foundation для ознакомления на практике с P4.

### Ход работы
1. Был склонирован репозиторий https://github.com/p4lang/tutorials и создана виртуальная машина с помощью команды vagrant up.
![1](https://user-images.githubusercontent.com/56114211/209585112-015792c6-5fc9-4dbd-b93c-46c03d43e136.png)

![2](https://user-images.githubusercontent.com/56114211/209585125-c36a2398-50c2-49b4-9339-e90eb30765b7.png)

2. Был выполнен вход под учетной записью p4/p4. В shell была выполнена команда make run, а затем проверена доступность узлов.
![3](https://user-images.githubusercontent.com/56114211/209585164-21b0a3c6-2e20-43ad-a80d-4425f03e2d1c.png)

3. Были внесены изменения в файл basic.p4:
    * Был обновлен парсер, который позволяет заполнять заголовки ethernet_t, ipv4_t.
    * ![4](https://user-images.githubusercontent.com/56114211/209585181-66af26e7-70b6-402a-9b21-9a208f8d3bd6.png)
    * Было дополнено action ip4_forward: был определен выходной порт, обновлен адрес назначения пакета, обновлен источник отправления пакета, уменьшено значение TTL.
    * ![5](https://user-images.githubusercontent.com/56114211/209585197-5881041c-3ec0-465a-aee1-67130d1fcb80.png)
    * Обеспечено применение ipv4_lpm, если заголовок ipv4 валидный.
    * ![6](https://user-images.githubusercontent.com/56114211/209585213-cc72d154-c290-424c-8049-dd1575b75d9b.png)
4. Была выполнена проверка скрипта.
![7](https://user-images.githubusercontent.com/56114211/209585243-dddfcb51-7685-47b1-acb6-1c5d5a304bce.png)

5. Был изменен файл basic_tunnel.p4:
    * Был обновлен парсер myParser, а именно, добавлена функция заполненения заголовка myTunnel.
    * ![8](https://user-images.githubusercontent.com/56114211/209585249-471f6080-d069-457e-b80f-97e80397bfb2.png)
    * Определено действие myTunnel_forward, которое назначает выходной порт.
    * ![9](https://user-images.githubusercontent.com/56114211/209585253-d4bc5bac-e190-471b-a5f4-239f7a7e94cd.png)
    * Определена таблица myTunnel_exact.
    * ![10](https://user-images.githubusercontent.com/56114211/209585254-fee931e6-d77b-48a4-ba98-b112c79cd47c.png)
    * Обновлено выражение apply, которое позволяет применять myTunnel_exact, если заголовок myTunell валидный.
    * ![11](https://user-images.githubusercontent.com/56114211/209585257-112ae402-4b58-482c-bf0e-e339c84d699c.png)
    * Был обновлен MyDeparser
    * ![12](https://user-images.githubusercontent.com/56114211/209585264-dc930606-1d82-4db6-a257-a759f6a86a64.png)

6. Была проверена локальная связность.
![13](https://user-images.githubusercontent.com/56114211/209585275-b6119bfb-081d-472a-be0f-5abc91a7e39c.png)
7. Был отправлен пакет с h1 на h2 с туннелированием.
![14](https://user-images.githubusercontent.com/56114211/209585284-f6691f66-86ff-4ee5-9851-3fd08ade4b20.png)

### Выводы
Таким образом, был изучен язык P4, который позволяет настраивать сетевое оборудование, были дополнены скрипты, которые позволяют корректно обрабатывать трафик и организовывать туннели.

Схема сети:
![15](https://user-images.githubusercontent.com/56114211/209585300-79b8c6da-a35f-48a7-a24c-80c5190698ba.png)

