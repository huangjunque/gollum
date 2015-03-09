# 立方网运维部门Wiki

## 目录

- [运维部门新同事须知] (Yun-Wei-Bu-Men-Xin-Tong-Shi-Xu-Zhi)
- [运维工作](Yun-Wei-Gong-Zuo)
- [模拟线上存储环境添加存储节点](Mo-Ni-Xian-Shang-Cun-Chu-Huan-Jing-Tian-Jia-Cun-Chu-Jie-Dian)
- [fsmetalogger转为master流程](fsmetaloggerZhuan-Wei-masterLiu-Cheng)
- [Operations](Operations)
- [Network](Network)
- [DNS](DNS)
- [网络测试](Wang-Luo-Ce-Shi)
- [F5测试](F5Ce-Shi)
- [MFS](MFS)
- [Nginx](Nginx)
- [Backup](Backup)
- [OnlineServers](OnlineServers)
- [交换机端口](Jiao-Huan-Ji-Duan-Kou)
- [交换机配置](Jiao-Huan-Ji-Pei-Zhi)
- [更新记录](Geng-Xin-Ji-Lu)
- [机房联系暂无](Ji-Fang-Lian-Xi)
- [更新单](Geng-Xin-Dan)
- [立方网服务器资料汇总](Li-Fang-Wang-Fu-Wu-Qi-Zi-Liao-Hui-Zong)
- [立方网网络信息](Li-Fang-Wang-Wang-Luo-Xin-Xi)
- [线上服务器调整](Xian-Shang-Fu-Wu-Qi-Diao-Zheng)
- [内部服务器](Nei-Bu-Fu-Wu-Qi)
- [办公内网管理暂无](Ban-Gong-Nei-Wang-Guan-Li)
- [运维资产管理暂无](Yun-Wei-Zi-Chan-Guan-Li)
- [网站项目管理暂无](Wang-Zhan-Xiang-Mu-Guan-Li)
- [网站部署(puppet)](Wang-Zhan-Bu-Shu-puppet)
- [网站升级](Wang-Zhan-Sheng-Ji)
- [网站日常维护暂无](Wang-Zhan-Ri-Chang-Wei-Hu)
- [网站日志管理](Wang-Zhan-Ri-Zhi-Guan-Li)
- [网站监控管理](Wang-Zhan-Jian-Kong-Guan-Li)





## Production 生产环境

类别|词条
-----|-------|--------|
**Server 服务器** | [在线服务器](Online-Servers)• [外网虚机对照表](external-Asset)• [OnlineServers(物理机)](OnlineServers)• [Nginx](Nginx)• [NFS](NFS) • [MFS](MFS)• [named（暂无）](named) • [convirt管理原kvm虚拟机方法](convirtGuan Li Yuan kvmXu Ni Ji Fang Fa) • [convirt虚拟机管理服务器](convirtXu Ni Ji Guan Li Fu Wu Qi) • [MySQL（暂无）](MySQL) • [Redis](Redis) • [RabbitMQ](RabbitMQ) • [Memcached](Memcached) • [Ehcache](暂无Ehcache) • [Tomcat](Tomcat) • [服务器性能测试](Fu Wu Qi Xing Neng Ce Shi) • [服务器硬件信息采集](Fu Wu Qi Ying Jian Xin Xi Cai Ji) • [服务器内存更改列表](Fu Wu Qi Nei Cun Geng Gai Lie Biao)
**High Availability 高可用** | [Nginx HA](Nginx-HA) • [MySQL HA](MySQL-HA) • [MySQL Replication](MySQL-Replication) • [Memcached Redis H](Memcached-Redis-HA)
**Backups 备份** | [当前状态（暂无）](Dang Qian Zhuang Tai) • [灾难恢复（暂无）](Zai Nan Hui Fu) • [离线备份（暂无）](Chi Xian Bei Fen) • [备份清单](Bei Fen Qing Dan)
**OSs 操作系统** | [自动化安装](Cobbler-Auto-Install) • [发行版升级（暂无）](Fa Xing Ban Sheng Ji) •[Puppet（暂无）](Puppet) • [YUM仓库（暂无）](YUMCang Ku)•[CentOS](CentOS)
**Datacenter 数据中心** |   [数据中心规范（暂无）](ShuShu Ju Zhong Xin Wei Hu Ri Zhi) • [数据中心维护日志（暂无） ](Shu Ju Zhong Xin Wei Hu Ri Zhi) • [数据中心迁移计划（14年5月）](Data-Center-Relocation) • 
**Network 网络** |  [网络架构设计（暂无）](Wang Luo Jia Gou She Ji) • [802.1Q（暂无）](802.1Q)• [LVS](LVS) • [链路聚合（暂无）](Lian Lu Ju He) • [IRF（暂无）](IRF) • [BGP](BGP) • [F5 BIG-IP（暂无）](F5 BIG-IP) • [IP分配](IP-Addresses)
**Applications 应用** |  [Webapp部署](WebappBu Shu) • [独立App部署（暂无）](Du Li AppBu Shu) • [应用依赖关系（暂无）](Ying Yong Yi Lai Guan Xi) • [App配置集中化管理（暂无）](AppPei Zhi Ji Zhong Hua Guan Li)• [App更新与部署](AppGeng Xin Yu Bu Shu)  •  [日志集中化](Ri-Zhi-Ji-Zhong-Hua)  •  [服务器优化](Fu-Wu-Qi-You-Hua)
**Monitoring 监控** | [当前服务状态（暂无）](Dang Qian Fu Wu Zhuang Tai) • [Nagios](Nagios) • [nagios组织结构](nagios-Hierarchical-structure)• [nagios监控规范](nagios-specification)• [Sensu](Sensu)• [Zabbix（暂无）](Zabbix)• [IDC-smokeping](smokeping)
**Metrics&Statistics 度量与数据统计** | [Dashing（暂无）](Dashing) • [jmxtrans（暂无）](jmxtrans) • [statsd（暂无）](statsd) • [Graphite](Graphite)
**Maps 计划与映射** | [批量任务（暂无）](Pi-Liang-Ren-Wu) • [目录地址（暂无）](Mu-Lu-Di-Zhi) • [脚本（暂无）](Jiao-Ben)
**Contact 联系**| [联系方式汇总](Lian-Xi-Fang-Shi-Hui-Zong)|
**外网服务器系统账户口令**| • [外网子系统](external_subsystem) • [在线服务器账户口令](external-secure)|
**Misc 其它**| [域名管理](Yu-Ming-Guan-Li) • |


## 规范管理
类别  |  词条
----------- | ------------
**资产管理规范**|[虚机申请规范](virtual-guifan)• |
**监控规范**|[nagios监控规范](nagios-specification)• |
**web规范**|[dns文件命名规范]()•|



## Sandboxing 沙盒(测试)环境

类别  |  词条
----------- | ------------
**server服务器**|[内网服务器资产](Nei-Wang-Fu-Wu-Qi-Xiang-Mu-Shuo-Ming) • [内网虚机对照表](internal-Asset) • 
**服 务** |  [DNS](DNS) • [FTP](FTP) • [代码版本控制](Dai-Ma-Ban-Ben-Kong-Zhi) • [资产管理](Zi-Chan-Guan-Li) • [文件共享服务](Wen-Jian-Gong-Xiang-Fu-Wu) • [持续集成（暂无）](Chi-Xu-Ji-Cheng) • [用户管理系统LDAP（暂无）](Yong-Hu-Guan-Li-Xi-Tong-LDAP)•
**项目**|[项目部署](Xiang-Mu-Bu-Shu) • [代码更新流程](code-updates-process)
**备份**|
**网络**| [网络拓扑](Network-topology) • [上网管理](Shang-Wang-Guan-Li) • [网络设备配置](Wang-Luo-She-Bei-Pei-Zhi) • [内网维护](Nei-Wang-Wei-Hu)
**desktop support**|[同事入职/离职电脑部署流程](New-employee-orientation-process) • [Panabit上网策略使用说明](panabit-manual) • [上网行为管理--Centos安装OCS+GLPI流程](install-osc-glpi-on-centos) • [上网行为管理--新接入网络的电脑部署流程](The-Internet-behavior-management) • 
**内网服务器系统账户口令**|[内网服务器账户口令](internal_secure) • [内网子系统](internal_subsystem) • |


## Labs 实验室
### Todos
- 简化自动汇报racktables脚本，使其能够判断服务器制造商自动获取信息并提交
- 通过ipmi获取超微服务器信息

### 生产环境
- 上线异地照片上传加速方案
- 监控方案
- 度量统计
- 日志集中管理 & 实时分析
- 备份（DB & FS）
- HA & nginx
- 架构遗留问题
- NOC服务整理（199.210）
- 部署管理平台开发（监控整合、度量）  
  -支持sandbox环境
- 配置集中化（运维）  
    - salt客户端与服务端的注册，保证所有的服务器都在salt master管理  
    - 线上重装系统后，ssh服务器配置，用户配置，防火墙，hosts等统一  
    - puppet管理yum源  

- 配置集中化（开发）  
    - Xconfig
    - Xdeployer

### 内网环境
- puppet管理（纳入配置集中化）
- 文件共享服务（基本要求完成）
- DNS管理
- 备份
- 项目部署
- 上网管理
- 资产管理 
- 监控 （Nagios监控常见项目，预采用zabbix逐步替换）
- 度量统计
- 用户管理（目前正在1.16上进行部署openldap测试，正在整合samba和Redmine）
- 邮件服务（逐步摆脱腾讯企业邮箱，预采用Postfix+ldap进行现有邮件的替换工作）
