# minerproxy
以太坊矿池代理中转软件ETH proxy. 采用GO语言编写，高可靠性，高并发，性能佳。中转性能媲美矿池直连，杜绝无故掉包导致算力损失现象。 支持SSL，适用于windows，linux服务器建立矿池中转连接，支持多个矿池同时中转。
#linux centos系统下载运行
yum install git         # 安装git
git clone https://github.com/sinlinks/minerproxy  #下载代理软件
cd minerproxy
chmod 777 minerproxy_linux_amd64   
nohup ./minerproxy_linux_amd64 &    #后台运行，注意：& 也需要复制，运行完再敲几下回车
tail -f nohup.out      #后台运行查看
