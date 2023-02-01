---
layout: post
title:  "大學專題演變流程"
date:   2021-09-01 14:00:36 +0800
categories: jekyll update
---




https://github.com/CMU-Perceptual-Computing-Lab/openpose

->Openpose_Video.py



https://www.sciencedirect.com/science/article/abs/pii/S0262885621000524#bb0095

-> 正規化:人體關節等比縮 (自訂各個關節長度)


https://medium.com/analytics-vidhya/human-pose-comparison-and-action-scoring-using-deep-learning-opencv-python-c2bdf0ddecba

-> DTW

### ---- Openpose座標怎麼定出來的 & 我們做的DTW與別人做的DTW差別


https://dtaidistance.readthedocs.io/en/latest/usage/dtw.html#

-> dtaidistance


https://medium.com/analytics-vidhya/human-pose-comparison-and-action-scoring-using-deep-learning-opencv-python-c2bdf0ddecba

-> L2

-> 原計算與新計算以及直接所有資料做比對得分數(dtw，dtw_ndim)，總共6種

原計算方式畫出不是 人形， 所以才有 新計算 方式

6種方式中哪個合理
