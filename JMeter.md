---
aliases: [jmeter, JMeter]
---

[Apache JMeter](https://jmeter.apache.org/) приложение на базе java. Для работы необходима установка java. Проверить, установлена ли она можно с помощью команды:
```sh
>>> java -version
```

Для установки на Ubuntu можно воспользоваться следующей комбинацией коменд:
```sh
>>> sudo apt update

>>> sudo apt install default-jre
```

После установки запускается через терминал:
```sh
>>> cd /home/.../apache-jmeter-5.4.2

>>>./bin/jmeter
```

Далее настраивается или открывается пакет с тестовым планом. Тестовый план - xml-файл.
Конфигурируемые группы потоков:
![](https://i.imgur.com/rR38Sei.png)

Группа потоков:
![](https://i.imgur.com/7C5ZRou.png)
Нас интересует:
* **Количество потоков** (пользователей) - сколько одновременно пользователей будет слать запросы к серверу. Поток выполняет запросы последовательно. В цикле поток пробегает семплеры (примеры запросов).
Количество зависит от целей и стандартной нагрузки на проект.
* **Rump-up период** (период прогрева) - время разброва потоков. Стартует постепенно, "размазывая" по этому времени.
* **Loop Count** - количество итераций по семплерам.
* **Thread lifetime** - по истечение этого времени поток убивается и пересоздается.

Структура дерева групп потоков.
![](https://i.imgur.com/lCiTOpL.png)
* **Группа потоков**
* **Контроллер** отвечает за выполнение логики под ним. Можно настроить добавление отчетов.
* **Http Request Default** задает общие для всех запросов параметры, например IP стейджа
![](https://i.imgur.com/l8Zgd8v.png)
* **Ноды семплеров**. Пустые поля наследются из Http Request Default.
![](https://i.imgur.com/qluFzbj.png)


## Как тестировать
Переходим в Aggregate Report.
Указываем файл, куда сохранять отчет, можно дополнительно фиксирвать только успешные или только ошибочные кейсы. В разделе Configure можно выбрать поля, которые будут отображаться в отчете.
![](https://i.imgur.com/Pkjsi2N.png)
Отчет запскается кнопкой Run ![](https://i.imgur.com/4YWOrYS.png).
Останавливается - Stop ![](https://i.imgur.com/dYXXy9N.png).
Перед запуском нового теста, нужно очистить старый ![](https://i.imgur.com/pZ19S55.png).


