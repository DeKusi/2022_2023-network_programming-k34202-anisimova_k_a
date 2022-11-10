University: [ITMO University](https://itmo.ru/ru/) 
Faculty: [FICT](https://fict.itmo.ru)
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming) 
Year: 2022/2023 
Group: K34202 
Author: Anisimova Ksenia Alekseevna 
Lab: Lab1 
Date of create: 29.10.2022 
Date of finished: 11.11.2022

# Лабораторная работа №1 "Установка CHR и Ansible, настройка VPN"

## Описание
Данная работа предусматривает обучение развертыванию виртуальных машин (VM) и системы контроля конфигураций Ansible а также организации собственных VPN серверов.

## Цель работы
Целью данной работы является развертывание виртуальной машины на базе платформы Microsoft Azure с установленной системой контроля конфигураций Ansible и установка CHR в VirtualBox

## Ход работы
#### Настройка OpenVPN-сервера
1. Получена виртуальная машина: network-programming-3 84.201.175.22 (Алексей М. Ксения А.) и приватный ключ.
2. Было осущствлено подключение к этой виртуальной машине по SSH.![2022-11-09_22-31-07](https://user-images.githubusercontent.com/56114211/201030604-da782be5-9e56-4ff1-be1d-3b48f2045716.png)

3. На машину были установлены python, pip v22.3 и Ansible, что подробнее показано у Алекеся.
4. Был создан OpenVPN сервер
5. Создан профиль Ksenia,в котором был скачан профиль profile.ovpn для настройки OVPN-клиента.![2022-11-10_00-53-18](https://user-images.githubusercontent.com/56114211/201031061-dba71992-d320-4dfc-b968-b6e0d27b5e1f.png)

5. В Network Settings/Protocol был выбран TCP, в Advanced VPN/TLS Control Channel Security было выбрано none.![2022-11-10_10-51-01](https://user-images.githubusercontent.com/56114211/201032332-116308b0-9297-4b8e-9c13-7cba73d25e24.png)
![2022-11-09_22-39-07](https://user-images.githubusercontent.com/56114211/201032386-2b651932-bf9a-401e-91a6-86036afd14e8.png)


#### Настройка OpenVPN-клиента на Mikrotic
1. На VirtualBox была создана виртуальная машина Mikrotic CHR.
2. На виртуальной машине включен сетевой адаптер для работы с WinBox.
3. В WinBox были загружены ключ и сертификат для настройки OpenVPN-клиента.![2022-11-09_23-12-08](https://user-images.githubusercontent.com/56114211/201032509-1ecdf53d-e61b-4583-affb-fa5c921244a0.png)

4. В разделе PPP были выполнены настройки клиента и после нажатия на Apply VPN-туннель был настроен.![2022-11-09_23-21-22](https://user-images.githubusercontent.com/56114211/201032559-40f6710f-0635-45bd-a2ec-b21e66872975.png)


#### Вывод
1. Через графический интерфейс настроен OVPN сервер;
2. Локально через VirtualBox поднят Mikrotik CHR;
3. Создан туннель между ними.
