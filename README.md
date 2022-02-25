# minerproxy
以太坊矿池代理中转软件ETH proxy. 采用GO语言编写，高可靠性，高并发，性能佳。中转性能媲美矿池直连，杜绝无故掉包导致算力损失现象。 支持SSL，适用于windows，linux服务器建立矿池中转连接，支持多个矿池同时中转。

#linux centos系统下载运行
----
    yum install git         # 安装git
    git clone https://github.com/sinlinks/minerproxy  #下载代理软件
    cd minerproxy
    chmod 777 minerproxy_linux_amd64   #设置权限
    nohup ./minerproxy_linux_amd64 &    #后台运行，注意：& 也需要复制，运行完再敲几下回车
    tail -f nohup.out      #后台运行查看'
#浏览器查看程序运行状态
----
    打开浏览器，在地址栏输入您的服务器的IP地址/密码， 例如输入：
    138.167.231.121/1234    #查看基本信息 138.167.231.121 为服务器的IP地址  后面加 /1234  其中1234为config.json文件中设置的后台登录密码
    138.167.231.121/cs12    #查看抽水记录 138.167.231.121 为服务器的IP地址  后面加 /cs12  其中cs12为config.json文件中设置的查看抽水信息的密码
#配置文件说明
-----
    {
	"ssl"            :  false,            //是否ssl模式   该参数采用默认值即可
    "httpPort"       :  80,               //浏览器查看后台信息的端口，采用默认值即可
	"isDevfee"       :  true,            //是否采用抽水模式  true  抽水  false 不抽水
	"devfee"         :  0.5,             //抽水比例 默认0.5%。  例如需要修改抽水比例为1.5%时，将该值改为1.5
	"devfeeAddr"     :  "0x179c804bE15Feb5D2Fa8cD111B2858D91934D30f",   //抽水地址，更改为你的钱包地址
	"httpLoginPsd"   :  "1234",     // 浏览器后台登录密码   浏览器地址栏输入138.167.231.121/1234 可查看中转信息
	"httpDevfeePsd"  :  "cs12",    // 浏览器查看抽水记录密码   浏览器地址栏输入138.167.231.121/cs12 可查看抽水记录
	 
	"poolList"       : [                     //中转矿池列表，支持同时进行多个矿池的代理中转
		{
			"name": "ethermine.org",             //矿池名称
			"poolurl": "eu1.ethermine.org",     //矿池URL，
                "poolPort": 14444,                 //矿池port
                "localPort":18888                  //中转服务器port， 该端口可根据自己的服务器进行设置，若服务器有防火墙，需要设置为打开该端口
	    	},                                   //其余矿池类似进行设置。注意严格按照json文件格式配置config文件
#开发者费用
---
开启抽水模式，0.2%的开发者费用,不开启抽水,仅中转，没有开发者费用
#联系方式
-----
如果您在使用中有任何问题，请联系我们：sinlinksmail@yandex.com
