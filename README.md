# God

全自动批量扫描

## 使用方法，将要扫描的全部url放在target目录下的url.txt里

到God.py同级目录下 python God.py 

ps：如果需要添加线程扫描 python God.py -x 线程数量

```
pip install -r requirements.txt

python God.py -x 1 -v 1 -p 1 -n 1 -a 1
```

结果会在xray目录下以html形式生成

安装chrome xray需要这个浏览器

## 更新

添加漏扫

    afrog

    nuclei

    vulmap

    pocbomber

    xray

原先会遗漏目标，更新后不再遗漏目标

[![Stargazers over time](https://starchart.cc/Pik-sec/God-auto.svg)](https://starchart.cc/Pik-sec/God-auto)
