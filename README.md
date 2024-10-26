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

#### Там увидите следующее:

![Alt-текст](images/grafana_image.jpg)


## Содержимое, что и зачем:

1. `blackbox.yml`: Этот конфигурационный файл описывает модули проверки доступности сервисов с помощью Blackbox Exporter для Prometheus. Каждый модуль настраивает тип проверки (HTTP, TCP, GRPC, ICMP), метод запроса, допустимые коды ответов.
2. `prometheus.yml`: Этот конфигурационный файл для Prometheus определяет задание blackbox, которое каждые 15 секунд использует Blackbox Exporter для проверки доступности указанных сервисов по модулям (например, HTTP, TCP, GRPC) на целевом сайте `https://ptsecurity.com`
3. Файл внутри dashboards - `availability_dashboard.json`: Этот JSON-файл представляет собой конфигурацию панели Grafana для мониторинга доступности ресурса `https://ptsecurity.com`
4. Файл: `provisioning/dashboards/dashboards.yml`: Этот файл конфигурации для Grafana настраивает автоматическую загрузку и обновление панелей из файловой системы. Он указывает, что панели в формате JSON будут загружаться каждые 10 секунд из директории `/var/lib/grafana/dashboards`
5. Файл: `provisioning/datasources/datasources.yml`: Эта конфигурация задаёт источник данных для Grafana, указывая Prometheus как основной источник. Данные берутся с сервера Prometheus по адресу `http://prometheus:9090`


