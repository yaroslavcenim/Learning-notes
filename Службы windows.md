---
tags: [windows, windows-30-days]
---
# Службы windows

Служба Windows — это процесс, который запускается в фоне, часто до входа.

Три главные учетные записи служб:
  LocalSystem - максимальный доступ, может читать sam
  Network Service - доступ в сеть от имени машины
  Local Service- минимальные права

Типы запуска:
0 = Boot (ядро, самый ранний)
1 = System
2 = Auto (автоматически при загрузке)
3 = Manual (по требованию)
4 = Disabled (отключена)

Команды: 
Посмотреть все службы: sc query
Полная конфигурация службы: sc qc "service"
Остановить запустить: sc start/stop
Изменить тип запуска: sc config "service" start= auto
Изменить учетную запись: sc config "service" obj=
Удалить службу: sc delete "service"