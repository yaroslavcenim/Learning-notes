---
tags: [windows, windows-30-days]
---
# Windows defender и ASR

Основные команды: 
  Get-MpComputerStatus
  Set-MpPreference -DisableRealTimeMonitoring $true
  Add-MpPreference -ExclusionPath "C:\Users\Public"
  Add-MpPreference -ExclusionProcess "meterpreter.exe"
  Remove-MpPreference -ExclusionPath "C:\Users\Public"

Как обходят Defender
1. Добавляют исключение на свою папку.
2. Отключают Real-Time Monitoring (если Tamper Protection выключен).
3. Шифруют payload.
4. Работают в памяти (fileless).
5. Используют LOLBins.

Для CRTP различай изучение защиты и её отключение. Команды изменения настроек выше — административные действия, а не универсальный обход. Tamper Protection и политики могут их блокировать. Выполнение в памяти и LOLBins не гарантируют отсутствия обнаружения. Базовая теория Defender/ASR нужна сейчас; глубину практики бери из своей версии курса.
