---
tags: [windows, windows-30-days]
---
# SMB, RDP, WinRM

SMB (Server Message Block) — протокол файлового обмена.
Порт: 445 (прямой SMB) или 139 (NetBIOS over TCP).
  Команды:
    net view \\\192.168.1.50
    net use Z: \\\192.168.1.50\C$
    net use Z: /delete
    dir \\\192.168.1.50\NETLOGON

RDP (Remote Desktop Protocol) — графический удалённый рабочий стол.
Порт: 3389.
Требует членства в группе Remote Desktop Users или Administrators.
  Команды:
    query session
    net localgroup "Remote Desktop Users"
    reg query
    "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections (0 - вкл, 1 - выкл)

WinRM (Windows Remote Management) — удалённое выполнение команд. (Один домен не обязателен; условия аутентификации, доверия и настройки транспорта различаются)
Порт: 5985 (HTTP) или 5986 (HTTPS).
Требует включения: Enable-PSRemoting.
Доступ зависит от прав на WinRM/PowerShell endpoint. По умолчанию PowerShell Remoting обычно доступен администраторам; возможна отдельная делегация. Одно членство в Remote Management Users не гарантирует доступ к любому endpoint.
  Команды:
    Enable-PSRemoting -Force (включить WinRM)
    Test-WSMan -ComputerName 192.168.1.50 (проверить)
    Enter-PSSession -ComputerName 192.168.1.50 -Credential (Get-Credential) (удалённая сессия)
    winrm quickconfig - быстрая настройка

Из Kali к Windows:
  SMB:
    smbclient -L 192.168.1.50 -U Administrator
    smbclient //192.168.1.50/C$ -U Administrator

  RDP:
    xfreerdp /v:192.168.1.50 /u:Administrator /p:Passw0rd

  WinRM:
    evil-winrm -i 192.168.1.50 -u Administrator -p Passw0rd