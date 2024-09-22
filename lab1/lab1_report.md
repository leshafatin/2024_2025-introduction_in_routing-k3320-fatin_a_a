University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)

Year: 2024/2025

Group: K3320

Author: Fatin Alexey Andreevich

Lab: Lab1

Date of create: 19.09.2024

Date of finished: 22.09.2024

# Отчёт по лабораторной работе №1 "Установка ContainerLab и развертывание тестовой сети связи"

***Цель:*** ознакомиться с инструментом ContainerLab и методами работы с ним, изучить работу VLAN, IP адресации и т.д.


## Ход работы

Первым делом было много попыток установки Ubuntu на виртуальную машину локально, но из-за особенностей их реализации на Mac, это не приводило к успешным результатам.

Была арендована базовая ВМ в Selectel, через SSH выполнялись шаги по настройке окружения (Docker, ContainerLab) и конфигурации сетевых нод.

В yaml-файле была задана топология сети, указанная на схеме

<img src="./imgs/schema.drawio.png" style="width:500px; height: auto; background: white">

### После задания конфигураций нод, проверим работоспособность:

<img src="./imgs/1.jpg" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">
<img src="./imgs/2.jpg" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">
<img src="./imgs/3.jpg" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### PC1
<img src="./imgs/4.jpg" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### PC2
<img src="./imgs/5.jpg" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">
<img src="./imgs/6.jpg" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">




