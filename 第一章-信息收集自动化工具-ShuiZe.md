信息收集自动化工具-ShuiZe 

**项目功能:**
只需要输入根域名即可全方位收集相关资产，并检测漏洞。也可以输入多个域名、C段IP等，具体案例见下文。

调用：脚本借用了ksubdomain爆破子域名和theHarvester收集邮箱

**安装方法一: 正常安装运行**

`$ git clone https://github.com/0x727/ShuiZe_0x727.git`

`$ cd ShuiZe_0x727` 

`$ chmod  777 build.sh` 

`$ sudo ./build.sh   //一定要用root权限执行`

`$  python3 ShuiZe.py -h   //查看工具用法`


安装方法二: Docker运行

```
$  apt install docker.io

$  docker pull yankovg/python3.8.2-ubuntu18.04

$  docker run -itd yankovg/python3.8.2-ubuntu18.04 bash

$  docker exec -it docker的ID /bin/bash

$  apt-get update

$  apt install git --fix-missing

$  apt install vim

$  rm /usr/bin/python3

$  ln -s /usr/local/bin/python3.8 /usr/bin/python3

$  python3 -m pip install --upgrade pip

$  git clone https://github.com/0x727/ShuiZe_0x727.git

$  chmod 777 docker_build.sh

$  ./docker_build.sh
```

`$  python3 ShuiZe.py -h`

   最好在配置文件里填入fofa、shodan、github、censys的API，这样效果最佳。
   请一定要配置fofa的api～～～最好是高级会员
   配置文件地址：iniFile/config.ini
Usage: 
	python3 ShuiZe.py -d domain.com
	python3 ShuiZe.py -d domain.com --justInfoGather 1
	python3 ShuiZe.py -d domain.com --ksubdomain 0
	python3 ShuiZe.py -c 192.168.1.0,192.168.2.0,192.168.3.0
	python3 ShuiZe.py -f url.txt
	python3 ShuiZe.py -n 1 -c 192.168.1.0,192.168.2.0 -p 1.1.1.1:1111
	python3 ShuiZe.py -n 1 -f url.txt -p 1.1.1.1:1111 --web 1
	python3 ShuiZe.py -n 1 -c 192.168.1.0,192.168.2.0 -v 1
	proxychains4 python3 ShuiZe.py -n 1 -f /result/2ddcaa3ebbd0/172.18.82.0.xlsx
	proxychains4 python3 ShuiZe.py -n 1 -w 1 -f /result/2ddcaa3ebbd0/172.18.82.0.xlsx
	python3 ShuiZe.py --mn masNmap.xlsx
	python3 ShuiZe.py --mn masNmap.xlsx -w 1
	python3 ShuiZe.py --fofaTitle 大学
	python3 ShuiZe.py --domainFile domain.txt
	

	Options:
	  -h, --help            show this help message and exit
	  -d DOMAIN, --domain=DOMAIN
	                        target domain
	  -c CSUBNET, --cSubnet=CSUBNET
	                        target cSubnet
	  -n ISINTRANET, --intranet=ISINTRANET
	                        Scan intranet value set to 1
	  -p PROXY, --proxy=PROXY
	                        Intranet proxy socks5 socks4
	  -f FILE, --file=FILE  /result/2ddcaa3ebbd0/172.18.82.0.xlsx
	  -w WEAK, --weak=WEAK  run weak password script
	  -v VPN, --vpn=VPN     Run in the case of vpn
	  --web=WEB             detect web in Intranet
	  --mn=MASNMAPFILE      run masscan nmap result
	  --fofaTitle=FOFATITLE
	                        run fofa title
	  --domainFile=DOMAINFILE
	                        run domain title
	  --ksubdomain=KSUBDOMAIN
	                        not run ksubdomain
	  --test=TESTDEMO       if test=1 then run testDemo
	  --justInfoGather=JUSTINFOGATHER
	                        just infoGather, not detect vul
	  --getSocks=GETSOCKS   get socks

案例: 
$ python3 ShuiZe.py -d    mi.com  
oad chinazApi: 
--------------------------------------------------去重后共计10个顶级域名--------------------------------------------------
['京ICP备10046444号-21', '', 'xiaomiprint.com', '2021-12-22']
['京ICP备10046444号-5', '小米TV', 'mitvos.net', '2021-08-16']
['京ICP备10046444号-9', '小米科技', 'mi.cn', '2021-08-16']
['京ICP备10046444号-2', '小米科技有限责任公司', 'miui.com', '2021-08-16']
['京ICP备10046444号-4', 'MIUI米柚', 'miui.cn', '2021-08-16']
['京ICP备10046444号-13', '米聊', 'miliao.com', '2021-08-16']
['京ICP备10046444号-1', '小米网', 'xiaomi.cn', '2021-08-16']
重后共计10个顶级域名

开始查询对外投资企业:40
查询对外投资企业【杭州新帕元科技有限公司】
查询对外投资企业【武汉壹捌壹零企业管理有限公司】
查询对外投资企业【小米汽车科技有限公司】
查询对外投资企业【广东横琴小米科技发展有限公司】



仅用于学习和工具测试~  