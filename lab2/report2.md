University: [ITMO University](https://itmo.ru/ru/) 
Faculty: [FICT](https://fict.itmo.ru)
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming) 
Year: 2022/2023 
Group: K34202 
Author: Anisimova Ksenia Alekseevna 
Lab: Lab2
Date of create: 23.11.2022 
Date of finished: 24.11.2022

# Лабораторная работа №2 "Развертывание дополнительного CHR, первый сценарий Ansible"

## Описание
В данной лабораторной работе на практике изучается система управления конфигурацией Ansible, использующаяся для автоматизации настройки и развертывания программного обеспечения.

## Цель работы
С помощью Ansible настроить несколько сетевых устройств и собрать информацию о них. Правильно собрать файл Inventory.

## Ход работы
#### Создание виртуальной машины на VirtualBox, установка CHR, организация OVPN-клиента
1. Была создана виртуальная машина CHR_2 на VirtualBox.
![2022-11-24_11-05-56](https://user-images.githubusercontent.com/56114211/203727143-1680c827-a1a6-4f91-813f-a690fefad6e4.png)

2. Были получены сертификат и ключ для OVPN-клиента mikrotic2. В WInBox были имортированы сертификат и ключ, настроен OVPN-клиент.
3. Проверена IP-связность между OVPN-сервером и СHR_2.
![2022-11-23_18-05-11](https://user-images.githubusercontent.com/56114211/203727654-aa6e662a-b7b8-4174-bebd-c3a2a4b57a92.png)


#### Настройка CHR-машин с помощью Ansible
1. Был настроен файл инвентаризации /etc/ansible/host.
![2022-11-24_11-22-01](https://user-images.githubusercontent.com/56114211/203730290-d9be04a8-59ef-49f8-a58d-ebbd2193af58.png)

2. Настроен сценарий Ansible для создания пользователя user_1 на роутерах, для настройки NTP-клиента и OSPF.
![2022-11-23_19-25-32](https://user-images.githubusercontent.com/56114211/203731185-0d5c1094-b142-43e8-a1f4-21ce72bb9579.png)

3. Был запущен playbook.
![2022-11-23_19-42-17](https://user-images.githubusercontent.com/56114211/203733671-73472811-8020-466e-8e29-df988a81e0b8.png)
![2022-11-23_19-42-38](https://user-images.githubusercontent.com/56114211/203733699-eda38cef-e645-4061-a4e2-efc5701bd65a.png)

4. Было проверено состояние микротиков.
![2022-11-23_19-55-20](https://user-images.githubusercontent.com/56114211/203734119-d2927e7b-304e-4694-aadd-7bfd663de970.png)
![2022-11-23_19-56-10](https://user-images.githubusercontent.com/56114211/203734141-004a83bc-8ba6-4ee3-b428-3813186f72af.png)


#### Вывод
Таким образом, были созданы Ansible-плейбуки для конфигурирования роутеров, был изучен протокол динамической маршрутизации OSPF.
