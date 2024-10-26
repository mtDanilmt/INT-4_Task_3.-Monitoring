# INT-4_Task_3.-Monitoring
Этот репозиторий для третьего задания DevOps. Monitoring

## Запуск и просмотр:

Для запуска мониторинга неоходимо установить Docker и Docker Compose:

<a href="https://docs.docker.com/engine/install/debian/">
    <img src="https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png" alt="Docker Logo" width="25"/>
    Установка на Debian 
</a>
<a href="https://docs.docker.com/engine/install/ubuntu/">
    <img src="https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png" alt="Docker Logo" width="25"/>
    Установка на Ubuntu
</a>

Запуск необходимо производить в корнейвой директории проекта командой: 

```
sudo docker-compose up -d
```

1. Для просмотра метрик необходимо перейти по адресу: 

```
http://localhost:3000
```

2. Авторизоваться по логину и паролю:
   
```
admin
```

3. Пройти по Dashbord'у "Проверка доступности PT"


![Alt-текст](images/grafana_image.jpg)





