# Subnet_Mask_Scanner
Finds the subnet mask of the connected network using python in linux



## Finding a subnet mask using "ip address" is confusing.

Because we have to first identify our adapter.Then we have to see its mask.This could be done easily using the "ip route" command. 


Command output:(ip route)
```
default via 192.168.0.1 dev wlp2s0 proto dhcp metric 600 
169.254.0.0/16 dev wlp2s0 scope link metric 1000 
172.17.0.0/16 dev docker0 proto kernel scope link src 172.17.0.1 linkdown 
192.168.0.0/24 dev wlp2s0 proto kernel scope link src 192.168.0.106 metric 600 
```


1. From this output using the default gateway we get the name of the adapter. i.e wlp2s0.
2. Extract the ip of wlp2s0 where there is "proto kernel".
3. Using python split and cut the required date.


Output of Scanner.py

```
Adapter name         : wlp2s0
Hostname             : joker
local ip             : 192.168.0.106
Classless address    : 192.168.0.0/24
Network IP address   : 192.168.0.0
Network Mask         : 24
```

Reference:
  https://ryanstutorials.net/linuxtutorial/cheatsheetgrep.php
  https://learnbyexample.github.io/learn_gnugrep_ripgrep/perl-compatible-regular-expressions.html
  https://www.cyberciti.biz/faq/grep-regular-expressions/
  https://fabianlee.org/2021/01/09/bash-grep-with-lookbehind-and-lookahead-to-isolate-desired-text/
  https://stackoverflow.com/questions/287871/how-do-i-print-colored-text-to-the-terminal-in-python
  https://realpython.com/python-ipaddress-module/


## The End
