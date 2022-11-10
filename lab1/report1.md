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
---
## Описание
Данная работа предусматривает обучение развертыванию виртуальных машин (VM) и системы контроля конфигураций Ansible а также организации собственных VPN серверов.

## Цель работы
Целью данной работы является развертывание виртуальной машины на базе платформы Microsoft Azure с установленной системой контроля конфигураций Ansible и установка CHR в VirtualBox

## Ход работы
#### Настройка OpenVPN-сервера
1. Получена виртуальная машина: network-programming-3 84.201.175.22 (Алексей М. Ксения А.) и приватный ключ.
2. Было осущствлено подключение к этой виртуальной машине по SSH.
3. На машину были установлены python, pip v22.3 и Ansible, что подробнее показано у Алекеся.
4. Был создан OpenVPN сервер
5. Создан профиль Ksenia,в котором был скачан профиль profile.ovpn для настройки OVPN-клиента.
5. В Network Settings/Protocol был выбран TCP, в Advanced VPN/TLS Control Channel Security было выбрано none.

#### Настройка OpenVPN-клиента на Mikrotic
1. На VirtualBox была создана виртуальная машина Mikrotic CHR.
2. На виртуальной машине включен сетевой адаптер для работы с WinBox.
3. В WinBox были загружены ключ и сертификат для настройки OpenVPN-клиента.
4. В разделе PPP были выполнены настройки клиента и после нажатия на Apply VPN-туннель был настроен.

#### Вывод
1. Через графический интерфейс настроен OVPN сервер;
2. Локально через VirtualBox поднят Mikrotik CHR;
3. Создан туннель между ними.