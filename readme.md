VPN Monitor - developed by Martin Larsen

----------- Installation ----------

1: cd to your jka/gamedata directory (not base folder)

2: make sure you enable 'set developer 1' in your JKA server's launch script (./linuxjampded +exec server.cfg +set developer 1) and your server is logging console output to a .txt file named log.txt (see bottom for an example)

3: import from github: git clone

4: Edit file 'vpnmonitor' with required input

5: chmod a+x vpnmonitor, chmod a+x installvpndb, chmod a+x startvpnmonitor

6: run installvpndb (./installvpndb)

7: run startvpnmonitor (./startvpnmonitor) 

8: If you run a daily restart script for the server, make sure you add ./startvpnmonitor after your server restart command. Otherwise log will be truncated on server restart.

-------------------------------------
