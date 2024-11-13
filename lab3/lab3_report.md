University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)

Year: 2024/2025

Group: K3320

Author: Fatin Alexey Andreevich

Lab: Lab3

Date of create: 26.10.2024

Date of finished: 02.11.2024

# Отчёт по лабораторной работе №3 "Эмуляция распределенной корпоративной сети связи, настройка OSPF и MPLS, организация первого EoMPLS"

Создадим топологию с помощью конфигурации в файле lab3.yaml, сконфигурируем сетевые устройства

<img src="./imgs/schema.png">

## R01.NY

<img src="./imgs/R01.NY.png">

## R01.LND

<img src="./imgs/R01.LND.png">

## R01.HKI

<img src="./imgs/R01.HKI.png">

## R01.SPB

<img src="./imgs/R01.SPB.png">

## R01.MSC

<img src="./imgs/R01.MSC.png">

## R01.LBN

<img src="./imgs/R01.LBN.png">

# Результаты пингов 

### PC1 -> SGI_PRISM:

<img src="./imgs/PC1->SGI_PRISM.png">

### SGI_PRISM -> PC1:

<img src="./imgs/SGI_PRISM->PC1.png">

# Traceroute

### из R01.SPB в 192.168.4.101 и 192.168.3.101

<img src="./imgs/traceroute.png">

Интересно, что выбор маршрута на R01.NY:eth3 проходит через R01.LBN, а на R01.NY:eth4 через R01.LND.

### Из R01.SPB в R01.NY и наоборот

<img src="./imgs/NY->SPB.jpg">
<img src="./imgs/SPB->NY.jpg">

Здесь выбор промежуточных маршрутизаторов совпадает












