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

第三部 结果回存放在各个漏扫的对应目录下！！

结果会在xray目录下以html形式生成

安装chrome xray需要这个浏览器

## 11月10日 更新

添加漏扫

    afrog

    nuclei

    vulmap

    pocbomber

    xray

原先会遗漏目标，更新后不再遗漏目标

[![Stargazers over time](https://starchart.cc/Pik-sec/God-auto.svg)](https://starchart.cc/Pik-sec/God-auto)
