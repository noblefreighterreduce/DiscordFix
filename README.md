<div align="center">

# <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=28 /> <a href="https://github.com/noblefreighterreduce/">noblefreighterreduce</a><a href="https://github.com/noblefreighterreduce/zapret-discord-youtube">/zapret-discord-youtube</a> <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=28 />

**НОВОЕ**: Ускорение Telegram Desktop — https://github.com/noblefreighterreduce/tg-ws-proxy  
Альтернативный вариант: https://github.com/bol-van/zapret-win-bundle  
Поддержать разработчика оригинального zapret можно [здесь](https://github.com/bol-van/zapret?tab=readme-ov-file#%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0)
</div>

> [!CAUTION]
>
> ### Поддельные страницы
> У меня нет других страниц и групп в Telegram или каналов на YouTube.  
> Любой источник вне этой страницы GitHub, который выдает себя за меня, — **подделка**.

> [!IMPORTANT]
> Исполняемые и системные файлы из [`bin`](./bin) взяты из [zapret-win-bundle/zapret-winws](https://github.com/bol-van/zapret-win-bundle/tree/master/zapret-winws) и [zapret/releases](https://github.com/bol-van/zapret/releases). Происхождение можно проверить по хэшам и контрольным суммам.
>
> #### Проверяйте загружаемые из интернета сборки перед запуском и не ищите их через Яндекс. В первых результатах поиска часто оказываются вредоносные файлы, а настоящий репозиторий не показывается.  

> [!WARNING]
>
> ### Антивирусы
> Антивирус может среагировать на WinDivert.  
> Для работы zapret нужен WinDivert — средство перехвата и фильтрации сетевого трафика.
> Им могут пользоваться как безопасные, так и вредоносные программы, но сам WinDivert вирусом не является.
>
> **Фрагмент из [`readme.md`](https://github.com/bol-van/zapret-win-bundle/blob/master/readme.md#%D0%B0%D0%BD%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D1%81%D1%8B) репозитория [bol-van/zapret-win-bundle](https://github.com/bol-van/zapret-win-bundle)*
>
> Некоторые антивирусы считают файлы WinDivert инструментами повышенного риска или хакерскими средствами: файл удаляется и помещается в карантин. Обычно детект называется `WinDivert` или `Not-a-virus:RiskTool.Multi.WinDivert`.
>
> Добавьте папку с zapret в исключения антивируса либо выключите обнаружение PUA (потенциально нежелательных приложений). Например, в Касперском есть настройка «Обнаруживать легальные приложения, которые злоумышленники часто используют для нанесения вреда». Если вы уверенно настраиваете исключения, предпочтительно добавить исключение; если нет — рекомендуется отключить обнаружение PUA.

## ⚙️ Использование

1. Настройте безопасный DNS (Secure DNS).
    * В Chrome включите «Использовать безопасный DNS» и выберите поставщика, отличный от «Поставщика по умолчанию».
    * В Firefox откройте «DNS через HTTPS», задайте режим «Персональный», выберите «Выбрать провайдера/поставщика» и укажите URL вручную. Например: `https://dns.google/dns-query` — Cloudflare может быть заблокирован.
    * В Windows 11 Secure DNS можно включить в настройках самой ОС — [инструкция](https://remontka.pro/dns-over-https-windows-11/). Этот способ рекомендуется пользователям Windows 11.
    * На роутерах Keenetic включите параметр «Транзит запросов». Если он выключен, настройка и работа Secure DNS на компьютере могут вызывать проблемы.

2. Загрузите zip- или rar-архив со [страницы последнего релиза](https://github.com/noblefreighterreduce/zapret-discord-youtube/releases/latest).

3. Откройте свойства архива и отметьте «Разблокировать». При использовании 7-Zip или PeaZip этот пункт можно пропустить.

4. Распакуйте архив в каталог, путь к которому не содержит кириллицу или специальные символы.

5. Запустите нужный файл:
    * Чтобы найти работающую стратегию: **`service.bat`** → `Run Tests` → `Standard tests` → `All configs`.
    * Чтобы включить автозапуск: **`service.bat`** → `Install Service` → выберите подходящую стратегию.

## ℹ️ Файлы и их назначение

- [**`general.bat ...`**](./general.bat) — запуск стратегии вручную.

  Ручной запуск удобен для проверки стратегий. Результат зависит от множества факторов, поэтому переберите варианты (**ALT**, **FAKE** и другие), пока не найдёте подходящий.

- [**`service.bat`**](./service.bat) — настройка автозапуска и дополнительные инструменты:
  - <ins>**`Install Service`** — добавить выбранную стратегию в автозапуск (`services.msc`).</ins>
  - **`Remove Services`** — удалить стратегию и WinDivert из служб.
  - **`Check Status`** — посмотреть состояние обхода и служб, включая стратегию автозапуска и WinDivert.
  - **`Game Filter`** — включить или выключить обход для игр и других сервисов, работающих с UDP и TCP на портах выше 1023.  
  После смены параметра перезапустите стратегию. В скобках отображается состояние: включено или выключено.
  - **`IPSet Filter`** — управлять обходом ресурсов из `ipset-all.txt`. Может пригодиться при проверке ресурса, который без zapret открывается.  
  В скобках показан текущий режим:
    - `none` — ни один IP не проверяется;
    - `loaded` — IP сверяются со списком;
    - `any` — фильтр применяется ко всем IP.
  - **`Auto-Update Check`** — включить или отключить автоматическую проверку обновлений.
  - **`Replace active fakes`** — заменить текущий используемый фейк на другой из `bin`.
  - **`Update IPSet List`** — загрузить актуальный `ipset-all.txt` из репозитория.
  - **`Update Hosts File`** — обновить hosts <ins>**для восстановления веб-версии Telegram и подключения к голосовому чату Discord**</ins>.
  - **`Check for Updates`** — проверить наличие обновлений.
  - **`Run Diagnostics`** — проверить распространённые причины неполадок zapret.  
  В конце можно очистить кэш <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=11 /> `Discord` — это может помочь, если приложение внезапно перестало работать.
  - **`Run Tests`** — проверить стратегии с помощью встроенной утилиты:
    - `Standard tests` — проверка ресурсов из `utils/targets.txt`;
    - `DPI checkers` — проверка DPI у разных провайдеров, включая Cloudflare и Amazon.

## ☑️ Частые вопросы и неполадки

### После запуска `general*` ничего не происходит

- При запуске стратегии отдельным BAT-файлом, а не через service, должен появиться `winws.exe` — процесс обхода, видимый на панели задач.  
Если процесса нет, обратитесь к [#522](https://github.com/noblefreighterreduce/zapret-discord-youtube/issues/522).

### Не подошла ни одна стратегия

- Откройте командную строку с правами администратора.
- Выполните команды по очереди:

    `netsh winsock reset`
  
    `netsh int ip reset all`
  
    `netsh winhttp reset proxy`
  
    `ipconfig /flushdns`
  
- Перезагрузите компьютер.

### Не открывается веб-версия Telegram

В **`service.bat`** выберите **`Update hosts file`**. Если файл hosts устарел, программа предложит обновить его вручную:  
  - Скопируйте весь текст из открытого Блокнота.
  - В появившейся папке откройте `hosts` в текстовом редакторе, запущенном от имени администратора.
  - Вставьте скопированное в конец файла `hosts` (либо замените аналогичные строки, если уже добавляли их ранее).
  - Сохраните изменения и проверьте подключение. Если оно не восстановилось, убедитесь, что файл действительно сохранился.

#### Этот способ не гарантирует результат. Если он не помог, используйте [Telegram Desktop](https://github.com/telegramdesktop/tdesktop/releases) с [локальным прокси](https://github.com/noblefreighterreduce/tg-ws-proxy) или любым публичным прокси.

### Обход не работает или перестал работать

> [!IMPORTANT]
> **Стратегии могут со временем перестать работать.**
> Стратегия, работавшая раньше, может перестать обходить ограничения после обнаружения.
> В репозитории есть разные стратегии. Если ни одна не подходит, создайте новую на основе одной из них, изменив параметры.
> О параметрах стратегий можно прочитать [здесь](https://github.com/bol-van/zapret/blob/master/docs/readme.md#nfqws).

- Убедитесь, что `service.bat` → `Run Diagnostics` не обнаружил ошибок.

- Проверьте, внесён ли адрес ресурса в списки доменов или IP.

- Испытайте другие варианты, например **`ALT`** или **`FAKE`**.

- При необходимости выполните полную переустановку по инструкции ниже.

- См. [#765](https://github.com/noblefreighterreduce/zapret-discord-youtube/issues/765).

### Как полностью переустановить или обновить программу?

- Сохраните добавленные вами ресурсы и данные.
- Перезапустите устройство.
- Откройте `service.bat` → `Remove Services`.
- Перейдите в `service.bat` → `Run Diagnostics`; исправьте найденные ошибки, а в конце введите Y.
- Удалите папку zapret.
- Скачайте свежий архив (`zapret-discord-youtube-...`) со [страницы релизов](https://github.com/noblefreighterreduce/zapret-discord-youtube/releases).
- Щёлкните архив правой кнопкой, откройте свойства и, если доступна отметка «Разблокировать», включите её. Нажмите «Применить», затем «ОК».
- Распакуйте архив в новую папку в корне диска. Используйте путь без пробелов и специальных символов.
- Запускайте разные скрипты `general`. После каждого проверяйте доступ к интернет-ресурсам. Если они недоступны, закройте программу через значок замка на панели задач и испытайте другую стратегию.
- Найдя рабочую стратегию, настройте её автозапуск через `service.bat` → `Install Service`.

### Игра или приложение не работает при включённом zapret

- В `service.bat` проверьте, что `Game Filter` установлен в **`disabled`**, а `IPSet Filter` — в **`none`**. Другие значения могут повлиять на доступ к ресурсам, которые вы не собирались фильтровать.

### Античит сообщает о WinDivert

- Следуйте [инструкции](https://github.com/bol-van/zapret-win-bundle/tree/master/windivert-hide).

### Windows 7 требует цифровую подпись драйвера WinDivert

- Замените `WinDivert.dll` и `WinDivert64.sys` в [`bin`](./bin) одноимёнными файлами из [zapret-win-bundle/win7](https://github.com/bol-van/zapret-win-bundle/tree/master/win7).

### После удаления через [**`service.bat`**](./service.bat) WinDivert остаётся в службах

1. Узнайте имя службы в командной строке Windows (`Win+R`, затем `cmd`):

```cmd
driverquery | find "Divert"
```

2. Остановите службу и удалите её, подставив имя из предыдущей команды:

```cmd
sc stop название_из_первого_шага

sc delete название_из_первого_шага
```

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=18 /> YouTube

- Настройте [Secure DNS](#%EF%B8%8Fиспользование).
- Отключите блокировщик рекламы: известно, что YouTube начал с ними бороться.
- Если раньше всё работало, проверьте остальные стратегии.
- Дополнительная информация: [#251](https://github.com/noblefreighterreduce/zapret-discord-youtube/discussions/251).

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=18 /> Discord

- Проверьте настройку [Secure DNS](#%EF%B8%8Fиспользование).
- Сначала выясните, на какой стратегии открывается YouTube, и запустите её.
- В `service.bat` запустите `Run Diagnostics` и очистите кэш Discord.
- Проверьте, помогла ли очистка в приложении Discord.
- Откройте Discord в браузере: https://discord.com/app. Если веб-версия работает, можно пользоваться ею.
- Если веб-версия тоже недоступна, повторите проверку с другими стратегиями: YouTube и Discord могут работать на разных вариантах.
- Дополнительная информация: [#252](https://github.com/noblefreighterreduce/zapret-discord-youtube/discussions/252).

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/5968/5968804.png" height=18 /> Telegram

- Попробуйте [tg-ws-proxy](https://github.com/noblefreighterreduce/tg-ws-proxy).
- Либо используйте бесплатный MTProto-прокси из интернета.

### Не работают игры

Игры различаются, поэтому проверить и исправить каждую из них невозможно.

Общий порядок действий:
- Обновите ipset через `service.bat` и включите `Game Filter`.
- Если проблема остаётся, попробуйте режим `ipset any`.

У режима `ipset any` есть побочный эффект: многие сайты могут перестать открываться. Не оставляйте его включённым постоянно. Вместо этого выясните все IP-адреса игры и внесите их в `ipset-all.txt`.

Если эти шаги не помогли, откройте обсуждение в разделе [Discussions](https://github.com/noblefreighterreduce/zapret-discord-youtube/discussions), а не issue, и дождитесь ответа других игроков.

### Не нашли ответ на свой вопрос

- Создайте [issue](https://github.com/noblefreighterreduce/zapret-discord-youtube/issues).

## 🗒️ Добавление адресов ресурсов

Списки можно дополнить вручную:
- **`list-general-user.txt`** — домены; поддомены учитываются автоматически.
- **`list-exclude-user.txt`** — домены, которые нужно исключить. Например, когда сеть указана в `ipset-all.txt`, но отдельный домен из неё фильтровать не нужно.
- **`ipset-all.txt`** — IP-адреса и подсети.
- **`ipset-exclude-user.txt`** — IP-адреса и подсети для исключения.
  - Файлы **`*-user.txt`** создаются при первом запуске `zapret` или `service.bat`.

## ⭐ Поддержка проекта

Поставьте этому репозиторию :star: в верхней правой части страницы, чтобы поддержать проект.

Поддержать разработчика оригинального zapret можно также [здесь](https://github.com/bol-van/zapret?tab=readme-ov-file#%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0).

## ⚖️ Лицензия

Проект распространяется по лицензии [MIT](https://github.com/noblefreighterreduce/zapret-discord-youtube/blob/main/LICENSE.txt).

## 🩷 Благодарность участникам проекта

[![Contributors](https://contrib.rocks/image?repo=noblefreighterreduce/zapret-discord-youtube)](https://github.com/noblefreighterreduce/zapret-discord-youtube/graphs/contributors)

💖 Благодарим отдельно разработчика [zapret](https://github.com/bol-van/zapret) — [bol-van](https://github.com/bol-van)
