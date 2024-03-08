# God简介

集成式，批量漏洞扫描器，集成 afrog nuclei vulmap pocbomber xray 五个漏扫

# 使用方法！！！请认真阅读

首先程序全部开源，如果杀软报毒误报，那么是poc的问题。整理了一份github上所有的poc放入nuclei目录下的Pikzl.zip中，里面的poc验证为yaml格式，会触发杀软误报，现在整理后如果不用nuclei可以不需要解压Pikzl.zip，如果需要再解压就可以直接用了，！！注意df杀软会删除误报的poc导致文件不完整！！

第一步 将要扫描的全部url放在target目录下的url.txt里

第二步 到God.py同级目录下 python God.py 注意需要用到哪个漏扫，那么请加上对应漏扫首字母参数，比如需要xray，那么请这样 python God.py -x 1 

如果需要线程速度更快 python God.py -x 1 这里的数字越多扫描完目标越快（线程数量）

```
pip install -r requirements.txt

python God.py -x 1 -v 1 -p 1 -n 1 -a 1
```

第三步 结果回存放在各个漏扫的对应目录下！！

结果会在xray目录下以html形式生成

安装chrome xray需要这个浏览器

# centos7 安装
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
yum install -y google-chrome-stable_current_x86_64.rpm
yum install libpcap-devel -y
cp /usr/lib64/libpcap.so /usr/lib64/libpcap.so.0.8
yum update glib2 -y 
```
测试安装
```
/opt/google/chrome/chrome --version
```
卸载Google浏览器
```
yum autoremove -y google-chrome
```
# ubuntu 安装
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb
```
再次运行xray你会发现又出现错误了，
```
[launcher] Failed to get the debug url: [0224/025251.434358:ERROR:zygote_host_impl_linux.cc(90)] Running as root without --no-sandbox is not supported. See https://crbug.com/638180.
```
原因是chrome的沙箱问题，不能以root用户运行。

#重点

解决方案
修改 /usr/bin/ 目录下的 google-chrome 配置文件
```
vim /usr/bin/google-chrome
```
找到如下
```
exec -a "$0" "$HERE/chrome" "$@"
exec -a "$0" "$HERE/chrome" "$@" 注释掉

添加
exec -a "$0" "$HERE/chrome" "$@"  --no-sandbox $HOME
重新运行xray脚本即可
```
## 11月10日 更新

添加漏扫

    afrog

    nuclei

    vulmap

    pocbomber

    xray

原先会遗漏目标，更新后不再遗漏目标

## 12月7日 更新

端口由 : 改成 _

[![Stargazers over time](https://starchart.cc/Pik-sec/God-auto.svg)](https://starchart.cc/Pik-sec/God-auto)


