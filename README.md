1) telnet 192.168.1.1
2) exec sh
3) mkdir /opt/packages/ && cd /opt/packages && curl -sOfL https://github.com/qzeleza/kvas/releases/download/v1.1.8/kvas_1.1.8-release_2_all.ipk && opkg install /opt/packages/kvas_1.1.8-release_2_all.ipk
4) cd /tmp && curl -O https://raw.githubusercontent.com/maikldolg/test/refs/heads/main/part1.lst && kvas import part1.lst

commands list:

1) kvas setup         - запускаем первоначальную настройку пакета
2) kvas add ya.ru     - добавляем ya.ru в список разблокировки. Для поддержкой регулярных выражений введите, при запросе - 'Y'.
3) kvas import ./list - добавляем хосты из файла в списочный файл.
4) kvas del google    - удаляем все хосты со словом google внутри, из списка разблокировки.
5) kvas show          - выводим все хосты из списка разблокировки.
6) kvas test          - тестируем работу всех служб пакета.
7) kvas debug > ./log - сохраняем журнал отладочной информации в файл.
8) kvas purge         - удаляем все доменные имена из списка разблокировки.
9) kvas uninstall full   - производим ПОЛНОЕ удаление пакета со всеми архивными копиями.


manuals:

1) https://itdog.info/tochechnoe-napravlenie-opredelyonnyh-podsetej-ip-adresov-i-domenov-na-keenetic/#использование
2) https://github.com/Corvus-Malus/XKeen

utilities:

1) https://iplist.opencck.org/ (domain\ipv4)
