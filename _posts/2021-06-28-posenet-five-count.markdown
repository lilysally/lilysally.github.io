---
layout: post
title:  "使用 posenet 呈現 5 種計算方式"
date:   2021-06-28 14:00:36 +0800
categories: jekyll update
---



###  5 種計算方式

![](https://i.imgur.com/JF7woFg.png)
 
```
1. 原計算:單一關節之所有幀數(frame)數據(x,y)當作分母
2. 原計算 + 改變排序 + 多維dtw(dtw_ndim)
3. 新計算:當前幀數(frame)的所有關節數據(x,y)當作分母
4. 新計算 + 改變排序 + 多維dtw(dtw_ndim)
5. 新計算 + 改變排序 + 多維dtw(dtw_ndim)，所有幀數比較
6.
```
 
 

### Human-Pose-Compare 的 score.py 探討

score.py 的內容分成三部分: L2 ， 資料排序 ， DTW  

以下是 原計算 跟 新計算 在上述部份的差別:

![](https://i.imgur.com/u89QFpm.png)

---



> python start_here.py --activity "punch - side" --video "true.mp4" --lookup "false.pickle"


### 1.原計算 解釋



![](https://i.imgur.com/49eogjM.png)

```
資料排序-> [[x,y,x,y]]
          
```

```
這邊的 dtw 用一維跟多維，不會改變 dtw
```

### 2. 原計算 + 改變排序 + 多維dtw(dtw_ndim)

![](https://i.imgur.com/UFv1Dsc.png)


```
改變排序 -> 維持 [[x,y],[x1,y1]]

```
```
=> 第二點比第一點分數高，是因為改變資料排序，以二維去進行dtw
```

### 3. 新計算:當前幀數(frame)的所有關節數據(x,y)當作分母

![](https://i.imgur.com/DcSlkXd.png)

![](https://i.imgur.com/pG5zFMv.png)


紅色框框 : 以當前幀數(frame)的所有關節數據(x,y)當作分母

```
=> 新計算方式比原計算方式分數低的原因?
L2  被打亂，進入for i in range(0,17)迴圈進行dtw時失去L2原有特性(進入迴圈資料特性不是1)

```

### 4. 新計算 + 改變排序 + 多維dtw(dtw_ndim)

![](https://i.imgur.com/Lu1Tv5m.png)


### 5. 新計算 + 改變排序 + 多維dtw(dtw_ndim)，所有幀數比較

![](https://i.imgur.com/ScbN6t6.png)

![](https://i.imgur.com/qzyliaT.png)


```
得到-180 這個分數，是因為ip:201,model=212，會有201個1跟212個1進行dtw
```

### 6.

![](https://i.imgur.com/j0U5Kv7.png)

![](https://i.imgur.com/ZN85kFw.png)



```
第5點改變L2以所有資料比較，為什麼得到分數高?
因為資料特性為1
```


----

### 6種計算方式架構圖 : 

![](https://i.imgur.com/TkcxZHt.png)

![](https://i.imgur.com/ruHtwd2.png)

![](https://i.imgur.com/EDxjj9J.png)


![](https://i.imgur.com/NSbITiz.png)


----


### 問題
 
```
1.會影響結果的不是DTW，而是套DTW前的資料「L2方式、date.shape(資料排序)」，最佳的資料排序為何?
2.目前比對結果尚無判斷何時「開始比對、結束比對」，這可能影響結果
3.openpose做點位移，捨棄現在的norm(改變長度)?
4.openpose是否也做resize?
```
