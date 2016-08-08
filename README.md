# rkn
# 1. создаем правила для снорта
run> cat dump.xml | get_urls    >local.rules  2>get_urls.log
run> cat dump.xml | get_domains >>local.rules 2>get_domains.log
run> cat dump.xml | get_https   >>local.rules 2>get_https.log
run> cat dump.xml | get_ips     >>local.rules 2>get_ips.log
# 2. копируем "local.rules" в каталог настроек для снорта. У меня, например, в /etc/snort/rules/local.rules
# 3. снорт запускаю
run> snort -N -D -c /etc/snort/snort.conf -i enp5s1 -P 65535
# где enp5s1 - интерфейс подключен на зеркалирующий порт коммутатора

