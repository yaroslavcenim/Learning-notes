---
tags: [windows, windows-30-days]
---
# SAM и SECURITY

SAM(security account manager)
Расположение: hklm\sam\sam\domains\account\users
Ключевые значения:
  F и V — бинарные структуры метаданных/данных учётной записи.
  Не интерпретируй их как готовые открытые пароли или простую таблицу хэшей; формат зависит от версии Windows.

SECURITY - хранит LSA Secrets
Расположение: hklm\security\policy\secrets
Что там лежит:
  Пароли служб
  Пароли для запланированных задач
  Кэш доменных входов находится отдельно в HKLM\SECURITY\Cache; это не NT hash для PtH.

Файлы на диске:
  C:\Windows\System32\config\SAM
  C:\Windows\System32\config\SECURITY
  C:\Windows\System32\config\SYSTEM 

Расшифровка SAM:
/usr/share/doc/python3-impacket/examples/secretsdump.py -sam sam.save -system system.save LOCAL

Если сохранил только куст:
/usr/share/doc/python3-impacket/examples/secretsdump.py -sam sam.save -system system.save -security security.save LOCAL