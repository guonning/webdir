#webdir

##wadir.php
基于php-aria2，需要安装aria2的支持。
简单的管理:
![wadir管理](http://git.oschina.net/uploads/images/2016/1222/153707_d010cd32_700748.png "管理")
![wadir](http://git.oschina.net/uploads/images/2016/1222/104906_4ae29aad_700748.png "wadir")
##more.php
创建不同的目录每个目录都放入more.php，需要修改密码[不要设置相同的密码]
每个账户一个目录，登入后只能添加种子。
缺点：
1.无限制 [只能通过aria2的配置文件修改全局配置]
2.每个用户都可以看到下载列表
##ffmpge.php
服务器可玩，vps没用，115 牛逼..

基本界面和之前类似:
![ffmpeg](http://git.oschina.net/uploads/images/2016/1219/040352_a973d056_700748.png "界面")
黄色的就是转换符号，未用到任何数据库,没有转换完成通知，调用时间根据你的设置的PHP脚本运行时间为止。
在线转码，请
```
disable_functions = passthru,system,chroot,scandir,chgrp,chown,shell_exec,proc_open,exec,proc_get_status,popen,ini_alter,ini_restore,dl,openlog,syslog,readlink,symlink,popepassthru,stream_socket_server
```
上面删去exec

已经修改脚本运行时间1000s：
```
max_execution_time = 1000; 
```
修改配置后记得重新启动php端：

服务端安装ffmpeg【windows请勿使用】
ubuntu 安装ffmpeg
```
sudo apt-get install ffmpeg
```
Vultr 5刀的转换速度:!VPS不要搞这个，你需要一颗强劲的CPU，用其他互联网的云转码也不错。
[vultr](http://git.oschina.net/uploads/images/2016/1219/035456_77bbf7bf_700748.png "转换速度")
默认是webm格式的视频修改

```
return "<span class=\"ffmpeg  text-primary\" value=\"?video=".$file."\"><span class=\"glyphicon glyphicon-refresh\"></span></span>|<a href=\"".$file."\" ><span class=\"glyphicon glyphicon-download-alt\"></span></a>";
```

改变为:


 ```
return "<span class=\"ffmpeg text-primary\" value=\"?video=".$file."&type=mp4\"><span class=\"glyphicon glyphicon-refresh\"></span></span>|<a href=\"".$file."\" ><span class=\"glyphicon glyphicon-download-alt\"></span></a>";
```






##gbk.zip
如果中文乱码请解压使用该脚本
##mobile.php
mobile.php放在你的网站根目录并且设置好你的所在目录权限即可[可以名称为修改为index.php]
1.图标图片预览支持IE浏览器
2.手机端自动缩放
只展示该目录以下的所有文件
通过添加禁止显示文件夹以及后缀文件来控制显示
例如:
```
$this->notex=array("php","js","tgz");//不允许显示的后缀名文件
$this->notdir=array("a","phpmyadmin");//不允许显示的文件夹
```

支持在线播放mp4视频和MP3音频以及PDF在线预览；
eg：http://172.82.191.216/

LNMP LAMP 一键包测试通过， **windows下惨不忍睹** 
列表
![手机端竖屏](http://git.oschina.net/uploads/images/2016/1211/041819_91a745b3_700748.png "手机端竖屏")
![手机端横屏](http://git.oschina.net/uploads/images/2016/1211/041925_10a0f77d_700748.png "手机端横屏")
图片浏览
![图片浏览](http://git.oschina.net/uploads/images/2016/1211/042006_bb2bc8db_700748.png "图片浏览")
视频播放:
![视频](http://git.oschina.net/uploads/images/2016/1211/042033_51ee13ad_700748.png "视频")
![视频](http://git.oschina.net/uploads/images/2016/1211/042056_71db3584_700748.png "视频")

PC视图
图片:
![图片](http://git.oschina.net/uploads/images/2016/1207/154018_72e6622d_700748.png "图片")
视频
![视频](http://git.oschina.net/uploads/images/2016/1207/154052_1201172a_700748.png "视频")
PDF
![PDF](http://git.oschina.net/uploads/images/2016/1207/154111_05f29a34_700748.png "PDF")

