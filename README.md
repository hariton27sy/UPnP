# UPnP
Различные скрипты и возможно мануалы для взаимодействие с устройствами через UPnP

## 1. Поиск UPnP устройств в сети
Чтобы найти устройства в сети поддерживающие UPnP, необходимо отправить __UDP__ дэйтаграмму на multicast адрес __239.255.255.250:1900__

В ответе в заголовке __Location__ находится адрес страницы с поддерживаемыми функциями. Для моего роутера эта ссылка:
>\<router_address\>:1980/InternetGatewayDevice.xml

## 2. Сервис WANIPConnection (по крайней мере так называется в устройствах Tenda)
Переходим по данной ссылке, получаем данные в формате xml. Рассмотрим данный сервис. Он позволяет настраивать динамическую привязку внешнего порта ко внутреннему, чтобы обходить ограничения NAT

Находим раздел с данным сервисом:
![Пример конфига](https://raw.githubusercontent.com/hariton27sy/UPnP/master/images/WanIPConnection.png)

Нас интересует тег __ControlURL__
## TODO
- [ ] Посмотреть статистику UPnP
- [ ] Установка привязки портов
- [ ] Удаление привязки
- [ ] Небольшой клиент для интерактивной работы с привязками
- [ ] Другие UPnP сервисы (если они есть)
