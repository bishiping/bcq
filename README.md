# 一、用到的四个镜像地址

- bitwarden：https://hub.docker.com/r/bitwardenrs/server
- qBittorrent：https://hub.docker.com/r/linuxserver/qbittorrent
- caddy：https://hub.docker.com/r/teddysun/caddy
- plex：https://hub.docker.com/r/linuxserver/plex

# 二、排坑
在部署`linuxserver/plex`过程中，我好几次第一次网页端访问plex程序，都没找到添加本地（安装plex的设备）视频的方法，我还试了试frp，也不行。

后来在网上搜，找到了这样一个办法：先在putty软件里面添加一个`tunnel`，设置好`Source port 8888（这个端口随意）`和`Destination 127.0.0.1:32400（这个端口是服务端plex端口）`，然后点击`Open`创建ssh连接，本地浏览器访问`http://127.0.0.1:8888/web`即可进入plex的配置设置。大致流程就是先创建一个账号，登陆上之后，它会自动扫描本地存在的plex程序，然后就可以加上了。
