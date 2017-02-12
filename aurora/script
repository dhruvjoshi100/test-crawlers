#!/bin/bash
s='172.16.86.222/aurora/rankings&page='
for i in {1..11}
do
	d=$s$i
	wget $d -O- |
	hxnormalize -x |
	hxselect -i "table.table-hover" | 
	lynx -listonly -dump -stdin >> input
done
file="input"
while read line
do
    wget $line -O- |
    hxnormalize -x |
    hxselect -i "div.col-md-9" |    
    lynx -stdin -dump >> final
done<"$file"


