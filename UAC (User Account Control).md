---
tags: [windows, windows-30-days]
---
# UAC (User Account Control)

UAC управляет повышением прав и использованием полного/фильтрованного токена администратора. Повышенный процесс администратора не становится автоматически SYSTEM: это разные контексты безопасности.

Уровни UAC:
  Always Notify - Максимальный. Запрос на любое изменение.
  Default - Стандарт. Без запроса для настроек Windows.
  Never Notify — запросы подавлены; это не то же самое, что полное отключение UAC через EnableLUA.

Проверка состояния: 
reg query "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v EnableLUA
reg query "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v ConsentPromptBehaviorAdmin

- EnableLUA = 1 — UAC включён. 0 — отключён.
- ConsentPromptBehaviorAdmin = 5 — Default.
- ConsentPromptBehaviorAdmin = 0 — повышение без запроса для администратора; не равнозначно EnableLUA = 0.