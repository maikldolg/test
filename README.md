1) telnet 192.168.1.1
2) exec sh
3) mkdir /opt/packages/ && cd /opt/packages && curl -sOfL https://github.com/qzeleza/kvas/releases/download/v1.1.8/kvas_1.1.8-release_2_all.ipk && opkg install /opt/packages/kvas_1.1.8-release_2_all.ipk

{
kvas setup         - запускаем первоначальную настройку пакета
kvas add ya.ru     - добавляем ya.ru в список разблокировки. Для поддержкой регулярных выражений введите, при запросе - 'Y'.
kvas import ./list - добавляем хосты из файла в списочный файл.
kvas del google    - удаляем все хосты со словом google внутри, из списка разблокировки.
kvas show          - выводим все хосты из списка разблокировки.
kvas test          - тестируем работу всех служб пакета.
kvas debug > ./log - сохраняем журнал отладочной информации в файл.
kvas purge         - удаляем все доменные имена из списка разблокировки.
kvas uninstall full   - производим ПОЛНОЕ удаление пакета со всеми архивными копиями.
}

manuals:
https://itdog.info/tochechnoe-napravlenie-opredelyonnyh-podsetej-ip-adresov-i-domenov-na-keenetic/#использование
https://github.com/Corvus-Malus/XKeen

utilities:
https://iplist.opencck.org/ (domain\ipv4)
