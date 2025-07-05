To allow conatiners to talk to eachother over different networks you need run the following commands:
```
ip route
```
This will output a list of networks with some showing the following format `172.xx.x.x/16 dev br-xxxxxxxxxxxx proto kernel scope link src 172.xx.x.x`
Take note of the networks startting with br-xxxxxxxxxxxx.
Then run the following 2 commands:
```
sudo iptables -I DOCKER-USER -i br-xxxxxxxxxxx1 -o br-xxxxxxxxxxx2 -j ACCEPT
sudo iptables -I DOCKER-USER -i br-xxxxxxxxxxx2 -o br-xxxxxxxxxxx1 -j ACCEPT
```