# README

Para arrancar el proyecto hay que instalar y arrancar Postgresql mediante los siguientes comandos en la consola:

       sudo apt install postgresql libpq-dev

       sudo systemctl start postgresql.service

Si a la hora de arrancar la db te da algún problema, yo lo subsané con los siguientes comandos:

       sudo -b unshare --pid --fork --mount-proc /lib/systemd/systemd --system-unit=basic.target

       sudo -E nsenter --all -t $(pgrep -xo systemd) runuser -P -l $USER -c "exec $SHELL"
       
Después vuelves a arrancar la db y listo :)

Para apagar la db se hace mediante el siguiente comando:

       sudo systemctl enable postgresql.service


* ...
