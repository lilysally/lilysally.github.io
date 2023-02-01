---
layout: post
title:  "DTW連線座標資訊取的原始資料"
date:   2021-05-29 14:00:36 +0800
categories: jekyll update
---

## 圖解



![](https://i.imgur.com/R8BBqOF.png)

### 抓出s1跟s2連線的陣列值

![](https://i.imgur.com/FFYBNIn.png)


```
from dtaidistance import dtw
s1=[0,0,1]
s2=[0,1,1,5]
distance, paths = dtw.warping_paths(s1, s2)
best_path = dtw.best_path(paths)
print(paths)
print(best_path)
print(distance)
x=[]
y=[]
for i in range(len(best_path)):
    x.append(best_path[i][0])
    y.append(best_path[i][1])
print(best_path)
print("—————————————————————————————————————————————————————————————————————")
print("x:",x)
print("—————————————————————————————————————————————————————————————————————")
print("y:",y)
print("—————————————————————————————————————————————————————————————————————")

for i in range(0,len(best_path)):
    print('s1:',s1[x[i]],"索引值為:",x[i],"s1的第",x[i]+1,"個元素")
    print('s2:',s2[y[i]],"索引值為:",y[i],"s2的第",y[i]+1,"個元素")

```

![](https://i.imgur.com/alIlMdE.png)

### 抓出  最小距離連線的值

![](https://i.imgur.com/fqUr62P.png)

```
from dtaidistance import dtw
s1=[0,0,1]
s2=[0,1,1,5]
distance, paths = dtw.warping_paths(s1, s2)
best_path = dtw.best_path(paths)
print(paths)
print(best_path)
print(distance)
x=[]
y=[]
for i in range(len(best_path)):
    x.append(best_path[i][0])
    y.append(best_path[i][1])
print(best_path)
for i in range(0,len(best_path)):
    print('paths:',paths[x[i]+1][y[i]+1],)
    print("索引值為:[%d][%d]" % (x[i]+1,y[i]+1))
```

![](https://i.imgur.com/xed2pQR.png)

### 問題： 陣列資料輸出成inf

![](https://i.imgur.com/ioOkKpV.png)


來源 : https://github.com/wannesm/dtaidistance

