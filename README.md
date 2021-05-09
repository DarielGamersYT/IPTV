# IPTV Xtream UI Copia De Respaldo

Ante la presente salida de Xtream UI como lo conociamos, nos hemos encargado de resubir el instalador y algunos de los fix mas usados

Aqui te dejamos los scripts :)


¿Requieres hospedaje para tu servidor de Xtream UI?

Contratalo con nosotros por un precio accesible, ademas que no te tendras que encargar del mantenimiento que estos servicios conllevan

Solo envianos inbox para iniciar los tramites o soporte del mismo Cetus Cloud


Scripts
>Install Xtream UI:
root#>apt-get update

root#>apt-get install libxslt1-dev libcurl3 libgeoip-dev python

root#>wget https://github.com/DarielGamersYT/IPTV/blob/main/install.py

root#>python install.py


>Update Xtream UI 22F:
root#>apt-get install unzip e2fsprogs python-paramiko -y && chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && rm -rf /home/xtreamcodes/iptv_xtream_codes/admin && rm -rf /home/xtreamcodes/iptv_xtream_codes/pytools && wget "https://github.com/DarielGamersYT/IPTV/blob/main/master.zip" -O /tmp/master.zip -o /dev/null && unzip /tmp/master.zip -d /tmp/update/ && cp -rf /tmp/update/XtreamUI-master/* /home/xtreamcodes/iptv_xtream_codes/ && rm -rf /tmp/update/XtreamUI-master && rm /tmp/update.zip && rm -rf /tmp/update && chattr +i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && chmod +x /home/xtreamcodes/iptv_xtream_codes/permissions.sh && /home/xtreamcodes/iptv_xtream_codes/permissions.sh && /home/xtreamcodes/iptv_xtream_codes/start_services.sh


>Fix GeoLite2:
root#>cd /home/xtreamcodes/iptv_xtream_codes/crons/ && cp servers_checker.php servers_checker.php.orgi && rm servers_checker.php && wget https://github.com/DarielGamersYT/IPTV/blob/main/servers_checker.php && sudo chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && sudo chmod 777 /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && sudo chmod 777 -R /home/xtreamcodes/iptv_xtream_codes/crons && sudo /home/xtreamcodes/iptv_xtream_codes/start_services.sh


>Auto initialize on boot:
root#>nano /etc/crontab

root#>@reboot root /home/xtreamcodes/iptv_xtream_codes/start_services.sh


>Monitor PID Fix:
root#>wget "https://github.com/DarielGamersYT/IPTV/blob/main/pid_monitor.zip" -O /tmp/pid_monitor.zip -o /dev/null && unzip /tmp/pid_monitor.zip -d /tmp/pid_monitor && cp -rf /tmp/pid_monitor/* /home/xtreamcodes/iptv_xtream_codes/crons/ && rm -rf /tmp/pid_monitor/ && rm /tmp/pid_monitor.zip && sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && sudo chmod 777 -R /home/xtreamcodes/iptv_xtream_codes/crons
