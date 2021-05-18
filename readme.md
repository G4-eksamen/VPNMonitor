VPN Monitor - developed by devon

//Big thanks to oreo for his great help and getting me started on the project :)

Converting to nodeJS soon.

Feel free to use, edit it, re-write it in any way you may find helpful for the community.

Version 0.9, 05/2-21

Player connects -> program intercepts -> call to DB is made -> DB returns user | breaks to listen for connections

DB returns no user -> API check is made to verify vpn/no vpn -> if no vpn passed to DB as verified IP 

-> if vpn adds to iptables

----------- Installation ----------

1: cd to your jka/gamedata directory (not base folder)

2: make sure you enable 'set developer 1' in your JKA server's launch script (./linuxjampded +exec server.cfg +set developer 1) and your server is logging console output to a .txt file named log.txt (see bottom for an example)

3: import from github: git clone

4: Edit file 'vpnmonitor' with required input

5: chmod a+x vpnmonitor, chmod a+x installvpndb, chmod a+x startvpnmonitor

6: run installvpndb (./installvpndb)

7: run startvpnmonitor (./startvpnmonitor) 

8: If you run a daily restart script for the server, make sure you add ./startvpnmonitor after your server restart command. Otherwise log will be truncated on server restart.

---------- Example startup script -----------

restart script that logs console output to 'log.txt' -- just start this with a screen command 

#!/bin/bash

echo "JKA startup script"

status=1
while [ $status -ne 0 ]
do
        ./linuxjampded +exec "server.cfg +set developer 1" >log.txt 2>&1
        status=$?

        if [ $status -ne 0 ]
        then
                date=`/bin/date`
                echo "Server crashed with status "$status" at "$date
        fi
done

echo "Server exited peacefully"


