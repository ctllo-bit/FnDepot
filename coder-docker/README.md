# VS Code桌面版
通过docker运行code-server，然后获取地址给到iframe，可以得飞牛桌面版本的VScode，有两种方式打开，一个是内嵌的桌面版本，另一个外链打开，手机也可以打开，让你可以随时都能编写代码，也打破的docker应用没有内嵌的先例。

## 在内嵌终端打包应用
1、飞牛打开ssh
2、用vscode命令连接
ssh user@192.168.1.100
参数：user飞牛用户名与飞牛IP
3、输入密码连接，开发目录中执行本地安装
appcenter-cli install-local

## 添加 vscode 官方插件仓库

[如何让 code-server 使用 vscode 官方插件仓库](https://www.rehiy.com/post/594/)

## SSH Key设置（高级）
这是 唯一标准、长期、被所有工具（含 code-server / Remote-SSH）支持的方式。
1、在 code-server 所在容器生成 key
ssh-keygen -t ed25519
一路回车即可（可以不设 passphrase）
--------------------------------------------------------------------------------
2、把公钥拷到飞牛机器
ssh-copy-id user@192.168.1.100
输入最后一次密码即可。
--------------------------------------------------------------------------------
3、在 code-server 所在机器编辑
nano ~/.ssh/config
加上：
Host mynas
    HostName 192.168.1.100
    User user
    RequestTTY yes
    RemoteCommand cd /vol1/1000/VscodeProject && exec $SHELL
--------------------------------------------------------------------------------
以后只要：
ssh mynas
就会自动进目录

