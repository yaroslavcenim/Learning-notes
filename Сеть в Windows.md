---
tags: [windows, windows-30-days]
---
# Сеть в Windows

ipconfig:
ipconfig /all                  — все настройки
ipconfig /displaydns    — DNS-кэш
ipconfig /flushdns        — очистить DNS-кэш
ipconfig /release          — освободить DHCP
ipconfig /renew            — запросить DHCP

netstat:
netstat -ano            — все соединения + PID
netstat -b                — какой процесс слушает порт

route:
route print
route add 10.0.0.0 mask 255.255.255.0 192.168.1.1
route delete 10.0.0.0

arp:
arp -a                  — ARP-таблица
arp -d *               — очистить ARP-таблицу