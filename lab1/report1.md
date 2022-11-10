University: [ITMO University](https://itmo.ru/ru/) 
Faculty: [FICT](https://fict.itmo.ru)
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming) 
Year: 2022/2023 
Group: K34202 
Author: Anisimova Ksenia Alekseevna 
Lab: Lab1 
Date of create: 29.10.2022 
Date of finished: 11.11.2022

# ������������ ������ �1 "��������� CHR � Ansible, ��������� VPN"
---
## ��������
������ ������ ��������������� �������� ������������� ����������� ����� (VM) � ������� �������� ������������ Ansible � ����� ����������� ����������� VPN ��������.

## ���� ������
����� ������ ������ �������� ������������� ����������� ������ �� ���� ��������� Microsoft Azure � ������������� �������� �������� ������������ Ansible � ��������� CHR � VirtualBox

## ��� ������
#### ��������� OpenVPN-�������
1. �������� ����������� ������: network-programming-3 84.201.175.22 (������� �. ������ �.) � ��������� ����.
2. ���� ����������� ����������� � ���� ����������� ������ �� SSH.
3. �� ������ ���� ����������� python, pip v22.3 � Ansible, ��� ��������� �������� � �������.
4. ��� ������ OpenVPN ������
5. ������ ������� Ksenia,� ������� ��� ������ ������� profile.ovpn ��� ��������� OVPN-�������.
5. � Network Settings/Protocol ��� ������ TCP, � Advanced VPN/TLS Control Channel Security ���� ������� none.

#### ��������� OpenVPN-������� �� Mikrotic
1. �� VirtualBox ���� ������� ����������� ������ Mikrotic CHR.
2. �� ����������� ������ ������� ������� ������� ��� ������ � WinBox.
3. � WinBox ���� ��������� ���� � ���������� ��� ��������� OpenVPN-�������.
4. � ������� PPP ���� ��������� ��������� ������� � ����� ������� �� Apply VPN-������� ��� ��������.

#### �����
1. ����� ����������� ��������� �������� OVPN ������;
2. �������� ����� VirtualBox ������ Mikrotik CHR;
3. ������ ������� ����� ����.