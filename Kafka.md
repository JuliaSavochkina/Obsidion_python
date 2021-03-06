---
aliases: [Kafka, kafka, кафка, Кафка]
---
```python

```

Кафка - это брокер очередей.

Основные свойства:
- распределенность
- отказоустойчивость
- высокая доступность
- данные согласованы
- высокая производительность
- горизонтальное масштабирование
- интегрируемость

Основные сущности:
- Broker
- Zookeeper
- Message (Record)
- Topic/Partition
- Producer
- Consumer

Функции брокера:
- Прием сообщений
- Хранение сообщений
- Выдача сообщений

Несколько брокеров объединяются в кафка-кластер, что дает такие функции как:
- Масштабирование
- Реплекация

![](https://i.imgur.com/htA1niY.png)

Zookeeper (небольшая БД):
- Состояние кластера
- Конфигурация
- Адресная книга (data)

![](https://i.imgur.com/9cjovCk.png)

Среди брокеров выделяется один брокер, который называется кафка-контроллером. Он обеспечивает консистентность данных.

