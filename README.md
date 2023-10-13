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
```
 Шаг 1
Установить виртуальную машину.
![image](https://github.com/Flameitser/TOIB2/assets/65831927/c088f9f1-8b15-4b1b-9a2a-04a63790cf13)






 Шаг 2
Создание суперпользователя super-Kurchenko.I.D.
sudo useradd super-Kurchenko.I.D
sudo usermod -a -G sudo super-Kurchenko.I.D
passwd super-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB-2/assets/65831927/e810e538-486f-4d6e-acd0-422598cffc89)

 Шаг 3
Создание группы group-BBMO-02-23.
sudo groupadd BBMO-02-23
![image](https://github.com/Flameitser/TOIB-2/assets/65831927/6e5ea018-d9b2-49f3-b2e0-9018d972c54f)

 Шаг 4
Создание обычного пользователя user-Kurchenko.I.D и добавление его в созданную ранее группу.
sudo useradd -U -m -s /bin/bash -G BBMO-02-23 user-Kurchenko.I.D
passwd user-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB-2/assets/65831927/1f9da57d-8c0d-4939-8e6b-ccb82fc4af4b)

# Шаг 5
Проверка наличия пользователя user-Kurchenko.I.D в группу group-BBMO-02-23.
groups user-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB-2/assets/65831927/af108ae8-5a1d-4d40-b6ba-a5fa206f11b2)
groups super-Kurchenko.I.D
![image](https://github.com/Flameitser/TOIB-2/assets/65831927/8d2af599-487d-4fba-a28d-f121812c76c5)

# Шаг 6
Наделить полномочиями user-Kurchenko.I.D.
sudo chmod 770 ~
sudo chown super-Kurchenko.I.D:BBMO-02-23 ~


# Шаг 7
Проверка механизмов разграничения доступа.
mkdir 1.txt
touch 1.txt
rm 1.txt

```
