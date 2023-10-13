# Отчет по ПР-2 "Идентификация и аутентификация"

## Задача
В данном задании выполнены следующие шаги:

1. Создана виртуальная машина на базе ОС Debian 12.
2. Создан пользователь super-Kurchenko.I.D и наделен привилегиями суперпользователя.
3. Создана группа group-BBMO-02-23.
4. Добавен пользователь super-Kurchenko.I.D в группу group-BBMO-02-23.
5. Проверено наличие пользователя в группе.
6. Создан пользователь user-Kurchenko.I.D и добавен в группу group-BBMO-02-23.
7. Продемонстрирована работа механизмов разграничения доступа.


## Шаги выполнения

 Шаг 1
Установить виртуальную машину.
![image](https://github.com/Flameitser/TOIB2/assets/65831927/c088f9f1-8b15-4b1b-9a2a-04a63790cf13)


 Шаг 2
Создание суперпользователя super-Kurchenko.I.D.
sudo useradd super-Kurchenko.I.D
sudo usermod -a -G sudo super-Kurchenko.I.D
passwd super-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB2/assets/65831927/bceaab4e-8e9c-480b-9910-fe0349d61602)


 Шаг 3
Создание группы group-BBMO-02-23.
sudo groupadd BBMO-02-23
sudo usermod -aG BBMO-02-23 super-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB2/assets/65831927/f1ae4a45-518f-42c3-b38a-9b918581a0dd)


 Шаг 4
Создание обычного пользователя user-Kurchenko.I.D и добавление его в созданную ранее группу.
sudo useradd -U -m -s /bin/bash -G BBMO-02-23 user-Kurchenko.I.D
passwd user-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB2/assets/65831927/303695b4-583c-48aa-9dc7-4bd8501f6415)


# Шаг 5
Проверка наличия пользователя user-Kurchenko.I.D в группу group-BBMO-02-23.
groups user-Kurchenko.I.D
groups super-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB2/assets/65831927/293b90b2-1581-4ef3-b040-1e848c5d307c)


# Шаг 6
Наделить полномочиями user-Kurchenko.I.D.
sudo chmod 770 ~
sudo chown super-Kurchenko.I.D:BBMO-02-23 ~


# Шаг 7
Проверка механизмов разграничения доступа.
mkdir 1.txt
touch 1.txt
rm 1.txt


