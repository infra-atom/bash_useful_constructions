# bash_useful_constructions
### №1
while sleep 3; do { ((/usr/bin/curl -w "%{time_total}\n" -o /dev/null -s -IL https://yandex.ru | tr '\n' ' ') && date | tr '\n' ' ' && hostname) }; done
**OUTPUT**
0.513081 Wed Oct 14 20:20:55 UTC 2020 cassandra
0.478568 Wed Oct 14 20:20:58 UTC 2020 cassandra

### №2
for X in `seq 10`; do curl -Ik -w "HTTPCode=%{http_code} num_connects=%{num_connects} time_connect=%{time_connect} TotalTime=%{time_total}\n" https://ya.ru -so /dev/null; sleep 1 ; done
**OUTPUT**
HTTPCode=302 num_connects=1 time_connect=0.299241 TotalTime=0.903266
HTTPCode=302 num_connects=1 time_connect=0.299548 TotalTime=0.904071
HTTPCode=302 num_connects=1 time_connect=0.294476 TotalTime=0.888013
HTTPCode=302 num_connects=1 time_connect=0.295004 TotalTime=0.890665

### №3
curl http://checkip.amazonaws.com
**OUTPUT**
52.77.255.209



date +'%Y-%m-%d %H:%M:%S' -d "@1684932703181"
55363-05-23 21:59:41
**OUTPUT**
date -d @1684932703181
**OUTPUT**
Mon May 23 21:59:41 UTC 55363
