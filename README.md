# Домашнее задание к занятию "`Disaster Recovery. FHRP и Keepalived`" - `Марченко Вячеслав Игоревич`


### Задание 1

Дана схема для Cisco Packet Tracer, рассматриваемая в лекции.
На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.

### Ответ
1. ![Ping](https://github.com/Takarigua/sflt-homeworks1/blob/8bbff5eccb960ea2e953658d37b367fc3934494b/img/1.png)
2. ![Routers](https://github.com/Takarigua/sflt-homeworks1/blob/8bbff5eccb960ea2e953658d37b367fc3934494b/img/2.png)
3. Файл - https://github.com/Takarigua/sflt-homeworks1/blob/e4841032c0fa7448235becf8e455bdd0dda9b676/homework.pkt

---

### Задание 2

Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного файла.
Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

1. Работает на обеих VM ![Keepalive both VM](https://github.com/Takarigua/sflt-homeworks1/blob/4b75d611bb937de2b6bd9129c1bc058c4efb716f/img/keepALL.png)
2. ВМ 2 стала мастером после выключения nginx на ВМ 1 ![VM2 Master after Shutdown nginx VM1](https://github.com/Takarigua/sflt-homeworks1/blob/4b75d611bb937de2b6bd9129c1bc058c4efb716f/img/VM2%20Master.png)
3. Скриншо того, что айпи перескочил на вм2 ![ip a vm1 and vm2](https://github.com/Takarigua/sflt-homeworks1/blob/4b75d611bb937de2b6bd9129c1bc058c4efb716f/img/ip%20.png)
4. Ссылка на сами файлы (скрипт и конфиг) - https://github.com/Takarigua/sflt-homeworks1/blob/4b75d611bb937de2b6bd9129c1bc058c4efb716f/Keepalived%20homework.zip

```
