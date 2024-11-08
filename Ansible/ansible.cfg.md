```
[defaults]
host_key_checking  = false
fact_caching = jsonfile
fact_caching_connection = /tmp/facts_cache
library = library
gather_facts = true
interpreter_python = auto

[connection]
pipelining = True

[ssh_connection]
pipelining = True
```

**host_key_checking** - Проверка SSH-ключа. 

**fact_caching** - Кэширование фактов. Каждый раз при подключении к серверу Ansible собирает информацию о нём. Чтобы избежать тормозов - кэшируем данные в json-формате.

**fact_caching_connection** - Путь, где храним кэшируемые данные.

**library** - Путь, где будут дополнительные модули (например, если пишем свои модули). Если кастомные модули не используешь - можно удалить.

**gather_facts** - Говорим Ansible, чтобы перед выполнением задач происходил сбор фактов (IP серверов, интерфейсы и т.д.).

**interpreter_python** - Указываем, какой интерпретатор Python использовать. Если установлено несколько версий, Ansible сам определит, что использовать.

**pipelining** - Полезно при медленных сетевых соединениях. Повышает производительность за счёт уменьшения количества операций передачи данных между хостами.