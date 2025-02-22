# 广州大学gzhu健康打卡脚本

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [广州大学gzhu健康打卡脚本](#广州大学gzhu健康打卡脚本)
  - [综合简介](#综合简介)
  - [详细教程](#详细教程)
  - [FAQ](#faq)
    - [Q: fork之后的仓库能更新吗？](#q-fork之后的仓库能更新吗)
    - [Q: 如果脚本运行失败怎么办？](#q-如果脚本运行失败怎么办)

<!-- /code_chunk_output -->

> ## 感谢
>
>感谢situ2001让我发现了白嫖github action服务器的新思路
>[他的项目链接](https://github.com/situ2001/gzhu_no_clock_in)
>
>本来没打算自己写的，主要是因为我用他写的脚本打卡失败的机率太高了，高得离谱
>
>那就自己写一个打卡脚本吧，这种重复性的劳动就应该交给自动化来做！

## 综合简介

1. 脚本的使用需要设置两个repository secrets：XUHAO和MIMA
它们的值分别对应你的学号和密码。
2. 脚本会在每天早上7点自动运行。
3. 如果你的github账号绑定了邮箱的话，当脚本运行失败时，githun会发送一封运行失败的邮件给你
4. 如果github没有发邮件，就代表脚本运行成功

前面的都没看懂也没关系，跟着下面操作就行

## 详细教程

1. 首先把该项目Fork一份（在网页右上角，点Fork前记得顺便点个Star哦~）
2. 然后点击如下图所示的地方，也就是你的账号名。

---
![1](/assets/1.png)

---
然后就来到下面这个界面

---
![2](/assets/2.png)

---
请按上图操作，先点Repositories，然后找到自己刚刚fork的项目，点击。

这样就进入到了你自己fork的项目，如下图

---
![3](/assets/3.png)

---
按上图中操作

1. 先点Settings按钮
2. 然后点Secrets按钮
3. 之后再点击Secrets的下拉菜单中的Actions，进入Actions secrets界面。

接着继续按下图操作

---
![4](/assets/4.png)

---
上图圈起来的是需要创建的两个Secrets，点击New repository secret进入创建界面，如下图

---
![5](/assets/5.png)

---

- 要创建的第一个Secret的Name为XUHAO，注意XUHAO要大写
- Value是你自己的学号
- 全部输入完成后点击图中圈起来的绿色按钮Add secrect来创建

---

- 接下来是第二个要创建的Secret，Name是MIMA，注意MIMA要大写。
- Value是你自己的密码
- 全部输入完成后点击图中圈起来的绿色按钮Add secrect来创建

继续操作

---
![6](/assets/6.png)

---
如上图先点击Settings按钮左边的Actions按钮,再点击绿色按钮，进入下图界面

---
![7](/assets/7.png)

---
如上图

1. 点击箭头1处蓝色的地方（因为是用的别人的项目做演示，所以名称会不一样，我的项目这里的名称是scrape，如下图）
2. 点击2处箭头Enable workflow

---
![8](/assets/8.png)

---
至此，全部配置完毕，自动打卡已经激活了

## FAQ

### Q: fork之后的仓库能更新吗？

如果fork下来的仓库在未来需要更新，点击Fetch upstream并fetch and merge即可

### Q: 如果脚本运行失败怎么办？

1. 如果你是第一次运行脚本，请先检查学号密码是否输入错误
2. 其它时候大多是因为打卡系统崩溃导致的打卡失败，这个我无能为力，请待打卡系统恢复后手动打卡
3. 如果你想查看程序运行日志和情况，请点击自己项目里的Actions选项卡，这里有程序运行的情况，时间等信息。你还可以点击进入每一个流程以查看详细运行情况
