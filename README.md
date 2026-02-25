# Лабораторная работа N3

## Цель работы

Ознакомиться с основами контейнеризации а также подготовить рабочее пространство для дальнейших лабораторных работ.

## Ход работы

> Установить Docker Desktop и проверить его работоспособность.

Docker Desktop был давно установлен и протестирован, ошибок не наблюдалось, хотел написать я, однако впервые за всё время при запуске docker engine появилась ошибка.

```cmd

running wslexec: An error occurred while running the command. Wsl/Service/RegisterDistro/CreateVm/HCS/0x800705aa: c:\windows\system32\wsl.exe --import docker-desktop <home>\appdata\local\docker\wsl\main c:\program files\docker\docker\resources\wsl\wsl-bootstrap.tar --version 2: exit status 0xffffffff

```

Решить данную проблему получилось через 3 команды в Power Shell:

- ```wsl --shutdown``` - полностью останавливает "windows subsystem for linux"
- wsl --unregister docker-desktop - удаление дистрибутива docker desktop из wls
- wsl --unregister docker-desktop-data - удаляет все данные (образов, контейнеров и вэйлюм докера)

После перезапуска системы и docker desktop был сделан экспериментальный запрос в старой учебной безе данных на postgresql. Как видим, всё работает.

![alt text](image/Screenshot_2.png)

![alt text](image/Screenshot_1.png)

## To be continued → 

## Источники

- [Решение проблем с docker через power shell](https://www.reddit.com/r/docker/comments/1ft6u6f/docker_desktop_unexpected_wsl_error/)