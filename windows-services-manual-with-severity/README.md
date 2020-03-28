[![N|zabbix logo](https://avatars1.githubusercontent.com/u/4561226?s=200&v=4)](https://www.zabbix.com/)
# Шаблон для мониторинга сервисов OS Windows с ручным фильтром и разными уровнями важности триггеров

> Принцип работы - на хосте нужно создать макросы с фильтром содержащим регульярное выражение которое отфильтрует нужные службы из общего списка  
>  
> Переменные(отличие в важности триггеров создаваемых автообнаружением):  
>  
> `{$SERVICE.NAME.MATCHES.INFORMATION}`  
> `{$SERVICE.NAME.MATCHES.WARNING}`  
> `{$SERVICE.NAME.MATCHES.AVERAGE}`  
> `{$SERVICE.NAME.MATCHES.HIGH}`  
> `{$SERVICE.NAME.MATCHES.DISASTER}`  
>  
> Пример регулярного выражения:  
> `^(service1|Service2)$` - сработает на `service1` и `Service2`  


**Установка:**

 1. Скопируйте скрипт `userparameter_alias_windows_services.conf` в `\path\to\zabbix\agent\zabbix_agentd.d`

> Файл содержит алиасы на service.discovery и service.info для работы нескольких автообнаружений.

 2. Импортируйте шаблон Zabbix `zabbix-4.4-template.xml`

> Данный шаблон совместим с версией Zabbix 4.4 и выше

 3. Перезапустите службу `zabbix-agent`

 4. Прикрепите шаблон к целевым хостам в Zabbix
