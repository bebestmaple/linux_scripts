#!/bin/bash

a=`lsb_release -a`
b="Debian"
c="CentOS"
d="Ubuntu"
echo "将开消耗您的流量，此脚本占用服务器下行带宽。"
echo "将与8秒后开始运行。"
sleep 8
echo 正在检测环境......

if [[ $a =~ $b ]];then
    echo "Debian"
    apt-get install screen -y
elif [[ $a =~ $c ]];then
    echo "CentOS"
    yum install screen -y
elif [[ $a =~ $d ]];then
    echo "Ubuntu"
    apt-get install screen -y
else
    echo $a
fi
echo "starting..."
echo "启动成功，若要停止，重启服务器即可。"
echo "请等待，界面即将自动关闭。"
sleep 3
screen_name=$"run"  
screen -dmS $screen_name  
cmd=$"while true ;do wget -O /dev/null https://ftp.ncbi.nih.gov/50GB; done;";  
screen -x -S $screen_name -p 0 -X stuff "$cmd"  
screen -x -S $screen_name -p 0 -X stuff $'\n'
