---
tags: [windows, windows-30-days]
---
# BitLocker, EFS и Credential Guard

BitLocker — шифрование всего диска.
Проверить статус: manage-bde -status


EFS (Encrypting File System) — шифрование отдельных файлов и папок.
Зашифрованые файлы в текущей директории: cipher /u /n
Зашифровать: cipher /e "file"
Расшифровать: cipher /d "file"

Credential Guard — защита хэшей в памяти.
Команды:
  Get-ComputerInfo -Property DeviceGuard*
 
  reg query HKLM\SYSTEM\CurrentControlSet\Control\LSA /v LsaCfgFlags
  0 — отключён.
  1 — включён с UEFI Lock.
  2 — включён без UEFI Lock.