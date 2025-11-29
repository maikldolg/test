-------------------------------------------------------- Kvas + AmneziaWG setup: --------------------------------------------------------

1) telnet 192.168.1.1/ssh admin@192.168.1.1
2) exec sh
3) opkg install curl
4) mkdir /opt/packages/ && cd /opt/packages && curl -sOfL https://github.com/qzeleza/kvas/releases/download/v1.1.8/kvas_1.1.8-release_2_all.ipk && opkg install /opt/packages/kvas_1.1.8-release_2_all.ipk

(if there are some problems, try mkdir /opt/tmp/ && cd /opt/tmp/ ...)

5) cd /tmp && curl -O https://raw.githubusercontent.com/maikldolg/test/main/kvas_routing/kvas.lst && kvas import kvas.lst

Commands List:

1) kvas setup         - запускаем первоначальную настройку пакета
2) kvas add ya.ru     - добавляем ya.ru в список разблокировки. Для поддержкой регулярных выражений введите, при запросе - 'Y'.
3) kvas import ./list - добавляем хосты из файла в списочный файл.
4) kvas del google    - удаляем все хосты со словом google внутри, из списка разблокировки.
5) kvas show          - выводим все хосты из списка разблокировки.
6) kvas test          - тестируем работу всех служб пакета.
7) kvas debug > ./log - сохраняем журнал отладочной информации в файл.
8) kvas purge         - удаляем все доменные имена из списка разблокировки.
9) kvas uninstall full   - производим ПОЛНОЕ удаление пакета со всеми архивными копиями.

Extra for kvas+vless:
1) /opt/etc/init.d/S24xray restart
2) nano /opt/etc/xray/kvas.json
3) kvas vpn set

Manuals:

1) https://itdog.info/tochechnoe-napravlenie-opredelyonnyh-podsetej-ip-adresov-i-domenov-na-keenetic/#использование
2) https://github.com/Corvus-Malus/XKeen

-------------------------------------------------------- XKeen + X-ray setup: --------------------------------------------------------

1) Entware for USB: https://help.keenetic.com/hc/ru/articles/360021214160-Установка-системы-пакетов-репозитория-Entware-на-USB-накопитель
2) Entware for NAND: https://help.keenetic.com/hc/ru/articles/360021888880-Установка-OPKG-Entware-на-встроенную-память-роутера
3) 3X-UI panel setup: bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)
4) XKeen setup: https://github.com/Corvus-Malus/XKeen?tab=readme-ov-file#установка-xkeen

Manuals:
1) https://github.com/MHSanaei/3x-ui
2) https://github.com/Skrill0/XKeen
3) https://www.vdsina.com/ru/qa/q/kak-ispolzovat-server-s-predustanovlennym-3x-ui

Commands List:
1) xkeen -status: Проверка работы
2) xkeen -start: Запуск
3) xkeen -stop: Остановка
4) xkeen -restart: Перезапуск
5) xkeen -ap 443,80: Добавить порты для работы (можно указать один или несколько портов через запятую)
6) xkeen -dp 443: Удалить 443 порт из рабочих портов (можно удалить один или несколько портов через запятую; если не указать конкретный порт, будут удалены все)
7) xkeen -cp: Показать с какими портами сейчас работает прокси-клиент
   
P.S.:
Команды для создания TLS сертификата
1) Создаем папку для файлов и переходим в эту папку:
mkdir cert
cd cert
2) Создаем закрытый ключ. secret.key - это имя ключа с форматом .key:
openssl genrsa -out secret.key 2048
3) Создаем запрос на подпись сертификата:
openssl req -key secret.key -new -out cert.csr
4) Отправляем запрос на подпись. 365 - срок действия подписи сертификата в днях, можно установить другой срок:
openssl x509 -signkey secret.key -in cert.csr -req -days 365 -out cert.crt
5) Узнать точное расположение папки с файлами:
pwd
6) Далее в панели указываем пути до файлов:
Путь к файлу публичного ключа сертификата панели:
адрес папки из пункта 5)/cert.crt
Путь к файлу приватного ключа сертификата панели:
адрес папки из пункта 5)/secret.key

-------------------------------------------------------- Some useful manuals: ----------------------------------------------------------

1) https://telegra.ph/Sozdaem-gostevoj-WireGuard-segment-na-Keenetic-s-dostupom-k-internetu-cherez-router-01-29
2) https://core.telegram.org/resources/cidr.txt
3) https://anyipa.me
4) https://iplist.opencck.org/ (domain\ipv4)
5) iperf3 -c ping.online.net -p 5205 -P 20
