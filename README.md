# DDoS-using-PCA
1. Install mininet
2. Install pox controller using command: pip install pox
3. Create a topology: sudo mn --topo=tree,depth=2,fanout=4 --switch=ovsk --controller=remote,ip=127.0.0.1,port=6633 
4. Forward the files: l3_detectPCA.py, detectionpPCA.py and PCA.py to the path: ~/pox/pox/forwarding
5. Open new terminal then wake up pox controller using command: sudo ~./pox/pox.py forwarding.l3_detectPCA
6. From mininet turning on xterm h1, h2, h16
7. From terminal h16, using command: script h16.txt and tcpdumpt -v to see recieved packets
8. In the h1 terminal, using command python3 ./DDoS/code/traffic.py -s 2 -e 16 to send normal traffic to host 2 to host 16
9. In the h2 terminal, using command python3 ./DDoS/code/attack.py 10.0.0.[number of host that you want attack]
You can see in the pox terminal, deltaY values were calculated and printed in the terminal. When controller detected DDoS attack, it will print a message on the controller terminal and block the IP src causing DDoS attack.
