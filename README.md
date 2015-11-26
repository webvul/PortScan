# PortScan
Port Scan By Nmap
一 功能：
   <1>使用NMAP扫描端口，扫描结果保存入库(MYSQL)
   <2>新增端口邮件报警
二 依赖
   <1>Python 模块：libnamp,ConfigParser
   <2>建表：data_portscan data_newport
       CREATE TABLE `data_portscan` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `hostname` varchar(256) DEFAULT NULL,
  `ip` varchar(32) DEFAULT NULL,
  `port` varchar(11) DEFAULT NULL,
  `service` varchar(128) DEFAULT NULL,
  `date` datetime(6) DEFAULT NULL,
  `last_date` datetime(6) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=113 DEFAULT CHARSET=utf8

CREATE TABLE `data_newport` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `ip` varchar(32) DEFAULT NULL,
  `port` varchar(11) DEFAULT NULL,
  `service` varchar(128) DEFAULT NULL,
  `date` datetime(6) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=18 DEFAULT CHARSET=utf8
三 代码说明
   <1>conf/conf.ini  配置nmap扫描参数、报警接收人、数据库信息
   <2>conf/ip.ini  需要扫描的IP列表
   运行:
       python portscan.py
