# VPS-ssrz


> 部分看了[参考文章](https://github.com/Alvin9999/new-pac/wiki/%E8%87%AA%E5%BB%BAss%E6%9C%8D%E5%8A%A1%E5%99%A8%E6%95%99%E7%A8%8B)，讲的很好，但是一些地方不够全面，博主将一些地方更细致化，简单易懂。
> 里面相关内容会更新，有问题评论。

# 一、购买VPS服务器 #
Ps: 博主买的是Vultr的VPS，主要是有充10美刀送50美刀的活动，而且最近新出了6美刀/月的高频
vultr注册地址： https://www.vultr.com/?ref=7777564-4F 
****
**vultr一些规则：（属于爱看不看，可以直接安装后面图开始）**
1）计费从你开通服务器开始算
2）同样的服务器位置，不同的宽带类型和地区所搭建的账号的翻墙速度会不同，这与中国电信、中国联通、中国移动国际出口带宽和线路不同有关。当账号搭建完成并进行了bbr加速后，测试下速度自己是否满意，如果满意那就用这个服务器位置的服务器。如果速度不太满意，就一次性开几台不同的服务器位置的服务器，然后按照同样的方法来进行搭建并测试，选择最优的
3）开通服务器时，当出现了ip，不要立马去ping或者用xshell去连接，再等5分钟之后，有个缓冲时间。完成购买后，找到系统的密码记下来，部署服务器时需要用到。
4）vultr服务商提供的vps服务器是单向流量计算，有的vps服务商是双向流量计算，单向流量计算对于用户来说更实惠。因为我们是在vps服务器上部署SSR服务端后，再用SSR客户端翻墙，所以SSR服务端就相当于中转，比如我们看一个视频，必然会产生流量，假如消耗流量80M，那么VPS服务器会产生上传80M和下载80M流量，vultr服务商只计算单向的80M流量。如果是双向计算流量，那么会计算为160M流量。
5）vultr服务器每月有流量限制，超过限制后服务器不会被停止运行，但是超出的流量会被额外收费。北美和西欧地区的服务器超出流量后，多出的部分收费为0.01美元/G。新加坡和日本东京（日本）为0.025美元/G，悉尼（澳大利亚）为0.05美元/G。把vultr服务器删掉，开通新的服务器，流量会从0开始重新计算。
****

#### 1.开始付款，最少10美金
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716195550517.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
#### 2.点击+号开始部署
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716195711456.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
#### 3.选第一个或者第二个，看价格选择
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716195850370.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
#### 4.选择版本和套餐
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716200138330.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716200324337.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
####  5.部署好的信息
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716200456822.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)

# 二、部署VPS服务器 
购买好服务器后需要进行连接，并进行原创部署，使用XShell。

#### 1.下载并安装软件 
XShell下载地址(家庭/学校版本，够用了)[XShell](https://www.netsarang.com/zh/free-for-home-school/)

如果你是苹果电脑操作系统，无需下载xshell，系统可以直接连接VPS。打开终端（Terminal），输入ssh root@ip 其中“ip”替换成你VPS的ip, 按回车键，然后复制粘贴密码，按回车键即可登录。粘贴密码时有可能不显示密码，但不影响， 参考设置方法 如果不能用MAC自带的终端连接的话，直接网上搜“MAC连接SSH的软件”，有很多，然后通过软件来连接vps服务器就行，具体操作方式参考windows xshell。

#### 2.新建进行基础设置
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019071620113921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716201207985.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716201231852.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
连接国外ip即服务器时，软件会先后提醒你输入用户名和密码，用户名默认都是root，密码是你购买的服务器系统的密码。

如果xshell连不上服务器，没有弹出让你输入用户名和密码的输入框，表明你开到的ip是一个被墙的ip，遇到这种情况，重新开新的服务器，直到能用xshell连上为止。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716201340340.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716201352296.png)
#### 3.CentOS6+/Debian6+/Ubuntu14+ ShadowsocksR一键部署管理脚本
脚本一：
①    `yum -y install wget`

②  `wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh`

脚本二(备用)：
① `yum -y install wget`
② 

    wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh
    chmod +x shadowsocksR.sh
    ./shadowsocksR.sh 2>&1 | tee shadowsocksR.log

##### 输入代码后出现下图 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716165030305.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_1,color_FFFFFF,t_70)
##### 然后安装、设置端口号和密码
1）输入数字1来安装SSR服务端。
（注：如果输入1后不能进入下一步，那么请退出xshell，重新连接vps服务器，然后输入快捷管理命令bash ssr.sh 再尝试。）
2）依次输入自己想设置的端口和密码 (密码建议用复杂点的字母组合，端口号为40-65535之间的数字)，回车键用于确认
（注：关于端口的设置，总的网络总端口有6万多个，理论上可以任意设置，但不要以0开头！但是有的地区需要设置特殊的端口才有效，一些特殊的端口比如80、143、443、1433、3306、3389、8080。）![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716165130909.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_1,color_FFFFFF,t_70)
##### 设置加密方式
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716165411140.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_1,color_FFFFFF,t_70)
##### 选择协议
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716165541560.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_1,color_FFFFFF,t_70)
1）这里选择的是v4协议，一般选择这个就好了
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716170108889.png)
2）再设置混淆插件-plain
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716170528988.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
**注意：如果协议是origin，那么混淆也必须是plain；如果协议不是origin，那么混淆可以是任意的。有的地区需要把混淆设置成plain才好用。因为混淆不总是有效果，要看各地区的策略，有时候不混淆（plain）或者（origin和plain一起使用），让其看起来像随机数据更好。（特别注意：tls 1.2_ticket_auth容易受到干扰！请选择除tls开头以外的其它混淆）**

##### 设备数、单线程限速和端口总限速设置(全部回车)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716170703446.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716170758972.png)
##### 等待部署完成
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716170859182.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716202602891.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
出现上述信息图就算完成了
# 三、一键加速VPS服务器
这里就根据新建服务器时选择的版本进行如下选择
#### ① 破解版锐速加速教程-6 ×64

破解版锐速加速，Vultr的服务器centos6系统官方进行了更新，导致目前不支持BBR的部署，但锐速应该是可以部署的，不可以的话是用第二种就行了

###### 1，先更换服务器内核（脚本只支持centos系统，其它系统可以直接尝试第二步）

  ①   `yum -y install wget`

 ②   `wget --no-check-certificate https://blog.asuhu.com/sh/ruisu.sh && bash ruisu.sh`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716171615857.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
出现上图时表示已成功替换内核并服务器自动重启。
**若没有重启，手动关闭再进行连接即可**

##### 2.一键安装锐速
代码如下：

    wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/serverspeeder/master/serverspeeder-all.sh && bash serverspeeder-all.sh

**有些内核不适合，部署过程中需要手动选择推荐的，当部署时出现以下字样：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716171955557.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
提示没有完全匹配的内核,随便选一个内核就行,按照提示来输入数字,**按回车键即可**

###### 3.安装成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716172219802.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
#### ② 谷歌BBR加速教程 - 7 ×64
代码如下：
 `yum -y install wget`
  

       wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
        chmod +x bbr.sh
        ./bbr.sh
###### 1.安装过程
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716191134420.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019071619230255.png)
该回车的回车，按任意键的就按，最后成功的画面如下
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716192453133.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
###### 2.检测并调试
1） 重启服务器重新连接输入代码

    lsmod | grep bbr 
若出现下图则安装成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716192623608.png)
2） 少部分人安装bbr脚本并重启后，几分钟过去了，发现xshell无法连接服务器且服务器ip无法ping通。解决方法是：开新服务器或者重装系统，然后先安装bbr脚本再安装ssr脚本，或者改用锐速加速脚本。
3）    如果创建的是centos7的服务器，安装bbr加速后需要使用命令关闭防火墙，否则无法使用代理。CentOS 7.0默认使用的是firewall作为防火墙。
    先安装命令：
   

     yum install firewalld 
    
 查看防火墙状态：
     
    firewall-cmd --state

停止firewall命令：

    systemctl stop firewalld.service

禁止firewall开机启动命令：

    systemctl disable firewalld.service
最后再输入状态命令看防火墙是否还在运行


# 下载SSR客户端 

#### 1.SSR客户端下载
**PC端**：[SSR客户端下载](https://garygeng.com/others/ssr-windows/)（下载好再安装目录里点击.exe就可以直接打开了）
（对于> = Windows 8或 .Net 4.0，使用ShadowsocksR-dotnet4.0.exe。
   对于<= Windows 7或 .Net 2.0，使用ShadowsocksR-dotnet2.0.exe。）
**MAC** ：
**Linux客户端**：
**安卓客户端** ：
**苹果客户端**：目前大陆App Store商店很多SS/SSR软件都被下架了，所以我们首先把自己的账号更改到其它国家，比如美国，然后就可以下载软件了，非常方便。更改账号国家方法：打开App Store——App——账号头像——账号——国家/地区——更改国家或地区——美国——同意协议——确认，之后会进行到填写信息的界面，完善并确认后你就会发现自己的App Store变成美区了，这样就可以自由下载SS/SSR软件了。比如：Potatso Lite、Potatso、wingy等。或者用爱思助手PC端安装Shadowrocket的ipa文件，Shadowrocket IPA文件下载及教程地址。[Shadowrocket IPA文件下载及教程地址](https://github.com/gfw-breaker/guides/wiki/iPhone%E4%BD%BF%E7%94%A8Shadowsocks%E7%BF%BB%E5%A2%99)
****
**【注意】第一次电脑系统使用SSR/SS客户端时，如果提示你需要安装NET Framework 4.0，网上搜一下这个东西，安装一下即可。NET Framework 4.0是SSR/SS的运行库，没有这个SSR/SS客户端无法正常运行。有的电脑系统可能会自带NET Framework 4.0。
需要的自取：**[NET Framework4.0下载](https://www.microsoft.com/zh-CN/download/details.aspx?id=17851)
****
#### 2.进行SSR设置 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716181143300.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_1,color_FFFFFF,t_70)
在对应的位置，填上服务器ip、服务器端口、密码、加密方式、协议和混淆即可。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716204723324.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
这里采用的是**搜百谷**的图片：[非常全的SSR介绍](https://sobaigu.com/how-to-use-ssr.html)

#### 3.本地浏览器设置
将浏览器的代理设置为（http）127.0.0.1和1080即可，账号的端口号就是你自己设置的。而要上网的浏览器的端口号是1080，固定的，谷歌浏览器也是在设置里找。
![!\[在这里插入图片描述\](https://img-blog.csdnimg.cn/20190716194330467.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70](https://img-blog.csdnimg.cn/20190716194431425.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716194505995.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716194534136.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716194559575.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
# 恭喜成功！！！
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716194004481.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
## 注意！
1.XSHELL警告       [1-解析方法](https://blog.csdn.net/wugenqiang/article/details/86554753)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716184350538.png)
2.vps的服务器操作系统不要用的太高，太高可能会因为系统的防火墙问题导致搭建的SSR账号连不上。如果某个系统不好用，可以选择其它的系统来尝试。
3. 配置bbr加速脚本，重启电脑后xshell无法连接服务器。如果你遇到这样的问题，只能把服务器删除了，重新搭建个新的，可以先配置bbr加速脚本再配置ss/ssr脚本。

## 一些问题
#### 1.全部设置好仍不能翻
原因一：先 Ping自己的IP，不能Ping的话就是被强了；
    能Ping就是其他原因。
 原因二：看本地电脑的防火墙、杀毒软件之类，都关下试试，再看看远程服务器的防火墙关了没，没关的话SSR是连接不上的。
 原因三：有的地区需要把混淆参数设置成plain才好用。因为混淆不总是有效果，要看各地区的策略，有时候不混淆（plain）让其看起来像随机数据更好。
 
#### 2.电脑能用但手机用不了
方法：如果你的手机用的是SS客户端，SS客户端没有填协议和混淆的地方，如果你部署的协议和混淆的时候没有选择兼容原版（SS版），因此手机是用不了的。这个时候你把协议弄成兼容原版、混淆也设置成兼容原版即可。或者直接将协议设置成origin且混淆设置成plain。
#### 

####  3.多人使用
如果你想把搭建的账号给多人使用，不用额外设置端口，因为一个账号就可以多人使用。一般5美元的服务器可以同时支持40人在线使用。
如果想实现支持每个用户(端口)不同的加密方式/协议/混淆等，并且管理流量使用，可以参考多用户配置脚本：

    wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssrmu.sh && chmod +x ssrmu.sh && bash ssrmu.sh 

安装后管理命令为：

    bash ssrmu.sh

**注意**：这个**多用户**配置脚本和**教程**内容的脚本**无法共存**！**要想用**这个脚本，**把之前的脚本卸载**，输入管理命令bash ssr.sh ，选择3，卸载ShadowsocksR即可卸载原脚本。

#### 4.vultr申请退款
vultr和其他的国外商家一样，都是使用工单的形式与客服联系，如果需要退款，直接在后台点击support，选择open ticket新开一个工单，选择billing question财务问题，简单的在文本框输入你的退款理由。比如：Please refund all the balance in my account。工单提交以后一般很快就可以给你确认退款，若干个工作日后就会退回你的支付方式。（全额退款结束后，账号可能会被删除）
如果英语水平不好，但是想和客服进行交流，可以用百度在线翻译，自动中文转英文和英文转中文。

#### 5.路由器设置账号 
路由器也可以配置ss/ssr账号，详见openwrt-ssr项目地址：https://github.com/ywb94/openwrt-ssr
#### 6. 使用搭建的SSR玩游戏
如果电脑想用搭建的ss/ssr账号玩游戏，即实现类似VPN全局代理，可以用SSTAP，具体方法可以网上搜索。

****

# 一些经常用的设置 


#### 1.修改账号信息
打开XShell输入代码就完事了

    bash ssr.sh 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190716210333588.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNDI5MjIw,size_16,color_FFFFFF,t_70)
