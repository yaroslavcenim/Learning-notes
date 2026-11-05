---
tags: [windows, windows-30-days]
---
# AppLocker

AppLocker — белый список приложений. Что не разрешено — то запрещено. 

Посмотреть текущую политику: 
  Get-AppLockerPolicy -Local

Проверить состояние: reg query "HKLM\SOFTWARE\Policies\Microsoft\Windows\SrpV2"

Обходы AppLocker
- Писать в разрешённые папки (C:\Windows\Temp)
- Использовать LOLBins (mshta, rundll32, InstallUtil)
- Слабые правила по Path
- Повысить привилегии и отключить через реестр

Уточнение: разрешённость пути и LOLBins зависит от действующей политики — универсального разрешения для C:\Windows\Temp нет. Для анализа учитывай эффективную политику, включая GPO, а не только Local. Отключение политики не равно пониманию работы в ограниченной среде.
