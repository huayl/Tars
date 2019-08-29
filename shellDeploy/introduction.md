# 目录
> * [1.实现功能](#main-chapter-1)
> * [2.软硬件要求](#main-chapter-2)
> * [3.脚本介绍以及调用关系](#main-chapter-3)
> * [4.脚本运行说明](#main-chapter-4)

# 1. <a id="main-chapter-1"></a>脚本实现功能
-  该脚本用于快速部署Tars环境

# 2. <a id="main-chapter-2"></a>软硬件环境要求
该脚本仅仅使用于物理机部署和虚拟机部署（包括云主机），不适用于容器部署
-  操作系统 CentOS 7
-  硬件要求：最低2核2G，建议4核8G
-  不支持容器环境，systemctl start 等语句在容器环境运行会出现错误

# 3. <a id="main-chapter-3"></a>脚本介绍以及调用关系 
文件夹中的三个脚本的说明：
-  shellDeploy.sh 为主入口脚本， 进行绝大部分安装操作。 shellDeploy.sh调用了mysqlConfig.sh以及importTarsWebSql.sh
-  mysqlConfig.sh 主要用于mysql数据库的配置，包括：用户名，密码，权限，数据库表项导入等等
-  importTarsWebSql.sh 用于导入TarsWeb的数据库表项

# 4. <a id="main-chapter-4"></a>脚本运行说明
-  该脚本运行时候，需要使用本机的IP地址做为入参，请先查看本机IP地址。如果是云环境的话，请输入小网IP地址。
-  该脚本中使用Mysql安装环境中的默认密码tars2015作为默认密码，仅供学习和演示使用。实际应用场景，请大家自行修改密码。
-  运行方式：进入目录执行./shellDeploy $LocalIPAddr, 其中LocalIPAddr为安装机器的IP地址。 例：./shellDeploy 192.168.0.1
-  Tars代码下载路径默认为：/usr/local/tarscode. 如果需要下载到其它路径进行安装，可手动修改shellDeploy中的CodePath=/usr/local/tarscode路径即可。

