# Homework 10.02

### Ответ на вопрос 1
#### Push

Агент автоматически отправляет метрики сразу после запуска, обеспечивая немедленное обнаружение и постоянный мониторинг. Скорость обнаружения не зависит от количества агентов.

Минимальная работа для агентов по периодической отправке фиксированного набора измерений. Агенты не имеют состояния и экспортируют данные сразу после их создания.

Push агенты изначально защищены от удаленных атак, поскольку они не прослушивают сетевые подключения.

Для агентов требуется минимальная настройка: интервал опроса и адрес коллектора. Брандмауэры должны быть настроены для однонаправленной передачи измерений от агентов к коллектору.

Низкие накладные расходы и распределенный характер модели push позволяют отправлять измерения чаще, позволяя системе управления быстро реагировать на изменения.

#### Pull

Обнаружение требует, чтобы сборщик периодически очищал адресное пространство, чтобы найти новых агентов. Скорость обнаружения зависит от интервала сканирования обнаружения и размера адресного пространства.

Нагрузка на центральный опросчик увеличивается с увеличением количества опрашиваемых устройств. Агентам часто требуется поддерживать состояние, чтобы опросчик мог получить метрики позже.

Опросчик должен быть настроен со списком устройств для опроса, учетными данными безопасности для доступа к устройствам и набором измерений для извлечения.

Двусторонняя связь, используемая при опросе, увеличивает задержку, поскольку соединения устанавливаются и аутентифицируются до того, как измерения могут быть извлечены.

Опросщик может запросить любую метрику в любое время.

### Ответ на вопрос 2

Prometheus - Гибридная  
TICK - PUSH  
Zabbix - Гибридная  
VictoriaMetrics - PUSH  
Nagios - PULL  

### Ответ на вопрос 3


curl http://localhost:8086/ping -v
```
*   Trying 127.0.0.1:8086...
* TCP_NODELAY set
* Connected to localhost (127.0.0.1) port 8086 (#0)
> GET /ping HTTP/1.1
> Host: localhost:8086
> User-Agent: curl/7.68.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 204 No Content
< Content-Type: application/json
< Request-Id: 4fa1fcc5-bc1e-11ec-8097-0242ac160003
< X-Influxdb-Build: OSS
< X-Influxdb-Version: 1.8.10
< X-Request-Id: 4fa1fcc5-bc1e-11ec-8097-0242ac160003
< Date: Thu, 14 Apr 2022 18:11:31 GMT
< 
* Connection #0 to host localhost left intact
```

curl http://localhost:8888 -v
```code
*   Trying 127.0.0.1:8888...
* TCP_NODELAY set
* Connected to localhost (127.0.0.1) port 8888 (#0)
> GET / HTTP/1.1
> Host: localhost:8888
> User-Agent: curl/7.68.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Accept-Ranges: bytes
< Cache-Control: public, max-age=3600
< Content-Length: 336
< Content-Security-Policy: script-src 'self'; object-src 'self'
< Content-Type: text/html; charset=utf-8
< Etag: "3362220244"
< Last-Modified: Tue, 22 Mar 2022 20:02:44 GMT
< Vary: Accept-Encoding
< X-Chronograf-Version: 1.9.4
< X-Content-Type-Options: nosniff
< X-Frame-Options: SAMEORIGIN
< X-Xss-Protection: 1; mode=block
< Date: Thu, 14 Apr 2022 18:05:53 GMT
< 
* Connection #0 to host localhost left intact
<!DOCTYPE html><html><head><meta http-equiv="Content-type" content="text/html; charset=utf-8"><title>Chronograf</title><link rel="icon shortcut" href="/favicon.fa749080.ico"><link rel="stylesheet" href="/src.9cea3e4e.css"></head><body> <div id="react-root" data-basepath=""></div> <script src="/src.a969287c.js">
```

curl http://localhost:9092/kapacitor/v1/ping -v
```
*   Trying 127.0.0.1:9092...
* TCP_NODELAY set
* Connected to localhost (127.0.0.1) port 9092 (#0)
> GET /kapacitor/v1/ping HTTP/1.1
> Host: localhost:9092
> User-Agent: curl/7.68.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 204 No Content
< Content-Type: application/json; charset=utf-8
< Request-Id: 7557a299-bc1e-11ec-809f-000000000000
< X-Kapacitor-Version: 1.6.4
< Date: Thu, 14 Apr 2022 18:12:34 GMT
< 
* Connection #0 to host localhost left intact
```
![1](https://raw.githubusercontent.com/Evgeniy-Nikolskiy/hw10.2/main/assets/1021.png)

### Ответ на вопрос 4

Скриншот с отображением метрик утилизации места на диске  
![2](https://raw.githubusercontent.com/Evgeniy-Nikolskiy/hw10.2/main/assets/1022.png)

### Ответ на вопрос 5

Метрики, связанные с docker  
![3](https://raw.githubusercontent.com/Evgeniy-Nikolskiy/hw10.2/main/assets/1023.png)
