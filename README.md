## IT Army of Ukraine Official Tool

#### [English version - click here](/README-EN.md)

- Власна база проксі забезпечує атаку з усіх кінців світу, що значно ускладнює захист від неї
- Ефективна робота з великою кількістю цілей одночасно
- Безліч різноманітних методів, як "класичних", так і авторських
- Ефективне використання ресурсів завдяки асихронній архітектурі
- Постійні покращення, оновлення відбуваються автоматично без втручання користувача

### ⏱ Останні оновлення

<details>
<summary>Натисність щоб розгорнути</summary>

- **10.07.2022** Додано можливість конфігурації через файл mhddos.ini. Додано пітримку мов DE | PL | LT
- **08.07.2022**
    - Для простоти встановлення, та захисту від несанкціонованого використання, програма відтепер розповсюджується у
      вигляді виконуваного файлу
    - Можливість задавати власні цілі прибрана - використовуються цілі IT Army of Ukraine
- **27.06.2022** Додано іспанську локалізацію - параметр `--lang es`
- **22.06.2022** Покращено продуктивність роботи. Параметр `--debug` більше не підтримується через негативний вплив на продуктивність
- **10.06.2022** Додано зручний спосіб вказати власний проксі напряму в команді запуску (параметр `--proxy`)
- **08.06.2022** Додано налаштування `--copies auto` для автоматичного вибору значення з врахуванням доступних ресурсів

</details>

### 💽 Встановлення та запуск

#### Windows

У нашому ПО немає вірусів, але деякі антивіруси визначають ПО для атак як потенційно небезпечне, і блокують файли.
Можливо, вам доведеться вимкнути свій антивірус, або дозволити виконання завантаженого файлу.
Окрім того, автоматичне оновлення може викликати підозри у антивіруса, у такому випадку вам треба буде оновлюватися вручну

1. Завантажте останню [x64 версію](https://github.com/porthole-ascend-cinnamon/mhddos_proxy_releases/releases/latest/download/mhddos_proxy_win.exe)
   (або [x86 версію](https://github.com/porthole-ascend-cinnamon/mhddos_proxy_releases/releases/latest/download/mhddos_proxy_win_x86.exe) за потреби)
   і збережіть у зручному місці
2. Щоб приєднатися до атаки, просто запустіть файл подвійним кліком

#### Linux

1. Завантажте останню
   версію [за посиланням](https://github.com/porthole-ascend-cinnamon/mhddos_proxy_releases/releases/latest/download/mhddos_proxy_linux)
   і збережіть у зручному місці
2. Відкрийте термінал, перейдіть до папки з файлом і виконайте `chmod +x mhddos_proxy_linux`
3. Запускайте з терміналу `./mhddos_proxy_linux`

Примітка: перевірено на Ubuntu >= 18.04 та подібних

#### macOS

1. Завантажте останню
   версію [за посиланням](https://github.com/porthole-ascend-cinnamon/mhddos_proxy_releases/releases/latest/download/mhddos_proxy_mac)
   і збережіть у зручному місці
2. Відкрийте Terminal, перейдіть до папки з файлом і виконайте `chmod +x mhddos_proxy_mac`
3. Далі, виконайте `./mhddos_proxy_mac` - з'явиться вікно з повідомленням про неможливість запуску
4. Зайдіть в Системні параметри > Безпека та приватність, та натисніть "Все одно відкрити"
5. Надалі запускайте або подвійним кліком по файлу, або з Terminal `./mhddos_proxy_mac`
   При старті може бути затримка до 10c, це нормально, будь ласка, дочекайтеся запуску

Примітка: перевірено на macOS >= 11 (Intel та M1)

#### Docker

1. Встановіть та запустіть [Docker](https://docs.docker.com/desktop/#download-and-install)
2. Запускайте командою `docker run -it --rm --pull always --net=host ghcr.io/porthole-ascend-cinnamon/mhddos_proxy`

### 🛠 Налаштування та параметри

При першому запуску в поточній папці буде створено файл **mhddos.ini**  
Відредагуйте його для зміни налаштувань

Зміна мови:

    lang    = ua | en | es | de | pl | lt

Запуск декількох копій (вкажіть "auto" для максимального значення, при наявності 3+ ядер CPU та стабільної мережі):

    copies  = 1 | 2 | auto

Додати ваш IP/VPN до атаки (при запуску через VPN або на виділеному сервері):

    vpn     = true

Кількість потоків на кожну копію:

    threads = 8000

Окрім того, параметри можна задавати у командному рядку у форматі `--lang en` та `--vpn`

Повний перелік опції доступний за командою `--help`

### 🐳 Комьюніті

- [Створення ботнету з 20+ безкоштовних серверів](https://auto-ddos.notion.site/dd91326ed30140208383ffedd0f13e5c)
- [Аналіз засобу mhddos_proxy](https://telegra.ph/Anal%D1%96z-zasobu-mhddos-proxy-04-01)
- [VPN](https://auto-ddos.notion.site/VPN-5e45e0aadccc449e83fea45d56385b54)

### ✪ Власні проксі

Для того, щоб вказати власні проксі використовуйте опцію `proxy`

    proxy = [socks4://114.231.123.38:3065, socks5://114.231.123.38:1080]

Якщо перелік проксі занадто великий, скористайтеся опцією передачі через локальний чи віддалений файл `proxies`,
кожен проксі з нового рядка

    proxies = proxies.txt | https://pastebin.com/raw/UkFWzLOt

Звичайно, ці опції доступні і з командного рядка

    --proxy socks4://114.231.123.38:3065 socks5://114.231.123.38:1080
    --proxies proxies.txt | https://pastebin.com/raw/UkFWzLOt

#### Підтримувані формати:

    114.231.123.38:3065
    114.231.123.38:3065:username:password
    username:password@114.231.123.38:3065
    socks4://114.231.123.38:3065
    socks5://114.231.123.38:3065:username:password
    http://username:password@114.231.123.38:3065

якщо протокол (`socks4`|`socks5`) не вказано, то буде обрано `http`
