# Лыков Александр КИБ-22

* ЗАДАНИЕ 1
~~~
Используйте команду sysctl -a

Предоставьте скриншот значений ТОЛЬКО показателей ниже (используйте команду фильтрации):

vm.dirty_background_bytes

vm.dirty_background_ratio
~~~
* ЗАДАНИЕ 2
~~~
Используйте команду systemctl list-units --type=service

Предоставьте скриншот наименование юнита, принадлежащее описанию Network Manager
~~~
* ЗАДАНИЕ 3
~~~
В каких случаях необходимо перезапускать демон системы инициализации. Напишите системную команду для перезагрузки утилиты (демона).

Какой командой узнать статус? Приведите скриншот вывода результата использования данной команды.
~~~
* ЗАДАНИЕ 4
~~~
Перечислите команды для работы с модулями в используемой выше системной утилите. В каких случаях мы используем эти команды и для чего? Опишите своими словами.
~~~
* ЗАДАНИЕ 5
~~~
Выполните systemd-analyze blame.

Укажите, какие модули загружаются дольше всего и почему.
~~~
* ЗАДАНИЕ 6
~~~
Приведите название команды с опциями, которая позволит просмотреть ошибки ядра за вчерашний день. (подсказка: Используйте команды фильтрации, как less, greep). (гуглим).  
~~~
* ЗАДАНИЕ 7
~~~
Приведите команду с опциями, которая выведет службы, которые не смогли запуститься в системе (гуглим).
~~~
***
* Ответы:
***
Задание 1

![Задание1](https://github.com/Veritas97/Prac5Osis/blob/main/FOTO/1.png)
***
Задание 2

![Задание2](https://github.com/Veritas97/Prac5Osis/blob/main/FOTO/2.png)
***
Задание 3
~~~
1. Если по какой то причине демон запустился с ошибками
в этом случае требуется перезапуск

2. Команда для перезапуска:

systemctl restart

3. Команда что бы узнать статус:

systemctl status "наименование демона"
~~~
![Задание3](https://github.com/Veritas97/Prac5Osis/blob/main/FOTO/4.png)
***
Задание 4

Systemd – это система инициализации и системный менеджер

Команды:
~~~
1. systemctl start - запуск и остановка сервиса

2. systemctl restart - перезапуск

3. systemctl reload - перезагрузка

4. systemctl enable - включение сервисов

5. systemctl disable - отключение сервисов

6. systemctl status - проверка состояния сервиса

7. systemctl list-units - просмотр списка текущих юнитов

8. systemctl list-unit-files - список юнит-файлов
~~~
***
Задание 5
![Задание5](https://github.com/Veritas97/Prac5Osis/blob/main/FOTO/3.png)

~~~
udisks2.service

Монтируется внешний диск без прав
и из за этого он долго запускается
~~~
***
Задание 6
~~~
systemd-analyze — предоставляет статистику по процессу загрузки системы, проверяет корректность unit-файлов и так же имеет возможности отладки systemd

Команда journalctl без параметров выводит на экран все записи

вывод записей с момента последней загрузки
journalctl -b

вывод записей за определенный период времени
journalctl -S "2020-02-17 12:00" -U "2020-02-17 12:10"

вывод записей, принятых от определенной службы
journalctl -u pptpd

вывод сообщений ядра
journalctl -k

вывод сообщений с определенным приоритетом, в данном случае будут выведены ошибки и более высокие приоритеты(crit, alert, emerg).
journalctl -p err

вывод сообщений в реальном времени
journalctl -f
~~~
***
Задание 7

* sudo systemctl list-unit-files --type=service

![Задание7](https://github.com/Veritas97/Prac5Osis/blob/main/FOTO/5.png)
***
