---
tags: [windows, windows-30-days]
---
# Windows firewall

Три профиля:

- Domain — когда компьютер в доменной сети.
- Private — домашняя или доверенная сеть.
- Public — общественная сеть (максимальная защита).

Правила бывают:

- Inbound (входящие) — кто может подключиться к тебе.
- Outbound (исходящие) — куда ты можешь подключиться.

Каждое правило имеет:

- Action — Allow или Block.
- Protocol — TCP, UDP, ICMP, Any.
- Port — локальный или удалённый порт.
- Direction — In или Out.
- Profile — Domain, Private, Public.

Команды:
  Состояние файрвола:
    netsh advfirewall show allprofiles

  Включить / выключить файрвол:
    netsh advfirewall set allprofiles state on
    netsh advfirewall set allprofiles state off

  Сбросить все правила к стандартным:
    netsh advfirewall reset

  Посмотреть все правила:
    netsh advfirewall firewall show rule name=all

  Создать правило (открыть порт):
    netsh advfirewall firewall add rule name="Open Port 8080" dir=in action=allow protocol=TCP localport=8080

  Создать правило для конкретной программы:
    netsh advfirewall firewall add rule name="Allow MyApp" dir=in action=allow program="C:\myapp.exe" enable=yes

  Удалить правило:
    netsh advfirewall firewall delete rule name="Open Port 8080"

  Заблокировать исходящий трафик на конкретный IP:
    netsh advfirewall firewall add rule name="Block Evil IP" dir=out action=block remoteip=10.99.99.99