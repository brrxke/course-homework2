# course-homework2

## task 1

---

```bash

ps aux --sort=-%cpu 2>/dev/null > processes.txt

```

Для проверки наличия данных: wc -l processes.txt, head -5 processes.txt

---

Вариант с ошибкой: pss aux --sort=-%cpu 2>/dev/null > processes.txt

Для просмотра ошибки: pss aux --sort=-%cpu

## task 2

```bash
 ps aux --sort=-%cpu | grep "^$USER" | head -10 | tee user_processes.txt
broke       7009  400  0.0   9540  4484 pts/0    R+   16:37   0:00 ps aux --sort=-%cpu
broke       1698  0.5  1.5 620660 73148 ?        Sl   16:27   0:03 /usr/bin/kdeconnectd
broke       1349  0.3  0.6 277604 30904 ?        Sl   16:27   0:02 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libgenmon.so 15 25165838 genmon Generic Monitor Show output of a command.
broke       1221  0.3  2.9 1269548 139540 ?      Sl   16:27   0:02 xfwm4
broke       1345  0.3  1.3 315624 64228 ?        Sl   16:27   0:01 /usr/lib/x86_64-linux-gnu/xfce4/panel/wrapper-2.0 /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libcpugraph.so 13 25165836 cpugraph CPU Graph Graphical representation of the CPU load
broke       1151  0.2  0.0 215416  3396 ?        Sl   16:27   0:01 /usr/bin/VBoxClient --draganddrop
broke       1290  0.1  1.3 1182672 66032 ?       Sl   16:27   0:00 xfdesktop
broke       1714  0.0  1.3 611076 64228 ?        Sl   16:27   0:00 /usr/bin/python3 /usr/bin/blueman-applet
broke       6793  0.0  0.1 307676  6680 ?        Ssl  16:37   0:00 /usr/lib/x86_64-linux-gnu/xfce4/xfconf/xfconfd
broke       1273  0.0  1.1 1121248 55916 ?       Sl   16:27   0:00 xfce4-panel


```

---

Также есть еще вариации:

### Добавление к файлу, без перезаписи:

ps aux --sort=-%cpu | grep "^$USER" | head -10 | tee -a user_processes.txt

### Вывод в терминал и файл и подсчет строк:

ps aux --sort=-%cpu | grep "^$USER" | head -10 | tee user_processes.txt | wc -l

Флаг -а переключает режим с перезаписи на дозапись.

---

## task 3

```bash
#перечеслением
nmap -p 22,80,443,21,25,3306 scanme.nmap.org
#диапазоном
nmap -p 1-1000 scanme.nmap.org
#перечисление + диапазон
nmap -p 22,80,443,8000-8100 scanme.nmap.org
#все порты
nmap -p- scanme.nmap.org
#сервисы + ОС
sudo nmap -sV -O -p 1-65535 scanme.nmap.org
#только порты grepable формат в терминал
sudo nmap -p- -oG - scanme.nmap.org

```

## task 4

