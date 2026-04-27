# coder 桌面版
通过root应用运行systemctl，然后获取地址给到iframe，可以得飞牛原生版本的VScode，有两种方式打开，一个是内嵌的桌面版本，另一个外链打开，手机也可以打开，让你可以随时都能编写代码。

## 安装方法

直接下载安装fpk

或

离线本地安装

1、在/vol1/1000目录，创建coderProject文件夹
2、去官网按架构，下载最新code-server-*.tar.gz包
3、上传到/vol1/1000/coderProject目录，安装此fpk包即可。


## 在内嵌终端打包应用

fnpack build #打包fpk
sudo appcenter-cli install-local  #执行本地安装
sudo appcenter-cli install-local --env config.env  #指定环境变量文件进行静默安装

当应用包含安装向导时，可以在开发目录中创建环境变量config.env文件，通过环境变量文件来跳过交互式配置。

环境变量文件使用简单的键值对格式：

### 应用配置
wizard_admin_username=admin
wizard_admin_password=password123
wizard_database_type=sqlite
wizard_app_port=8080
