---
layout: post
title:  "使用Jekyll 形成一個靜態Blog"
date:   2023-02-01 14:00:36 +0800
categories: jekyll update
---




### [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)

符合官網所需要的Ruby，RubyGems，GCC and Make
```
Ruby version 2.5.0 or higher
RubyGems
GCC and Make
```
之後開始在cmd輸入指令:

```
gem install jekyll bundler
```
使用 jekyll 建立[myblog]資料夾
```
jekyll new myblog[資料夾]
```
資料夾結構如下:

![](https://i.imgur.com/wTnWElX.png)

移到 myblog 資料夾下
```
cd myblog
```
開始建立網站並讓它在本機上可以執行
```
bundle exec jekyll serve
```

在網址列上輸入 [http://localhost:4000](http://localhost:4000)，看到的畫面為

![](https://i.imgur.com/3PVDJF1.png)

### 恭喜成功使用 Jekyll 完成在本機(127.0.0.1)下的靜態Blog

