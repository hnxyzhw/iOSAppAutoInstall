介绍

# iOSAppAutoInstall

通itms-services://协议安装ipa，省去https环境的搭建，和SSL证书的配置

## 原理

使用Apple的itms-services://协议,在IOS7.1系统以后，如果要使用企业证书(299美元)通过itms-services在线安装ipa的话必须走https协议，其实需要https协议访问的只是manifest.plist文件的地址如:`itms-services://?action=download-manifest&url=https://appInfo/manifest.plist`， 但是 ipa的下载不需要走https协议也是可以的。

因此我们就建立一个web项目可以不用支持https，然后把我们的项目提交的GitHub（GitHub是https协议的或者其他https网站如码云等）仓库，然后获取到manifest.plist文件的地址替换为 上面plist文件的地址。最后，启动我门本地的服务访问下载页面即可。

## 安装APP时需要配置的链接

`"itms-services://?action=download-manifest&url=https://raw.githubusercontent.com/hnxyzhw/iOSAppAutoInstall/master/manifest.plist"`


