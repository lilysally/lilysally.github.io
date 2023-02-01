---
layout: post
title:  "Laravel工作坊Day2"
date:   2020-07-17 14:00:36 +0800
categories: jekyll update
---

## Day2
### 兩天上課的資源 : [20200710-17_Laravel 工作坊](https://www.dropbox.com/sh/smckyemt1i82les/AADi1B9bL2w0hIP2JJaI6Hk8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B?dl=0&subfolder_nav_tracking=1)



------


* [20190125-4_Model & Seeding.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AABugKXoa_Wdq286zcyIPfwca/20190124_Laravel%E8%AA%B2%E7%A8%8B(%E4%B8%89%E5%A4%A9)/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190125-4_Model+%26+Seeding.pdf&subfolder_nav_tracking=1)
* [20190126-1_Eloquent ORM.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AABugKXoa_Wdq286zcyIPfwca/20190124_Laravel%E8%AA%B2%E7%A8%8B(%E4%B8%89%E5%A4%A9)/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190126-1_Eloquent+ORM.pdf&subfolder_nav_tracking=1)
* [20190126-2_CRUD.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AABugKXoa_Wdq286zcyIPfwca/20190124_Laravel%E8%AA%B2%E7%A8%8B(%E4%B8%89%E5%A4%A9)/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190126-2_CRUD.pdf&subfolder_nav_tracking=1)
* [20190126-3_驗證與訊息.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AABugKXoa_Wdq286zcyIPfwca/20190124_Laravel%E8%AA%B2%E7%A8%8B(%E4%B8%89%E5%A4%A9)/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190126-3_%E9%A9%97%E8%AD%89%E8%88%87%E8%A8%8A%E6%81%AF.pdf&subfolder_nav_tracking=1)
----
### 20200717 檔案 :

* [20200717-3_Eloquent ORM.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200717-3_Eloquent+ORM.pdf&subfolder_nav_tracking=1)
* [20200717-5_檔案上傳.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200717-5_%E6%AA%94%E6%A1%88%E4%B8%8A%E5%82%B3.pdf&subfolder_nav_tracking=1)

-----
### 統整 Day1 上了甚麼




----

### 對應講義 :  [20200717-1_Migration & Schema.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200717-1_Migration+%26+Schema.pdf&subfolder_nav_tracking=1)


### 設定超連結

* url()
* route()

### name() 
使用者 : url
開發者 : 參數

只要使用 name() 方法，來自動調整 參數修改，必須要一個個的手動調


### Migration : 

新增 posts 資料表

![](https://i.imgur.com/0PDbtgF.png)

建立好 posts 資料表的內容

![](https://i.imgur.com/81FPpyA.png)


### rollback

artisan migrate:rollback 

![](https://i.imgur.com/BViS0zv.png)

![](https://i.imgur.com/dmHflw9.png)

![](https://i.imgur.com/pmFGg6r.png)

![](https://i.imgur.com/lUFIScJ.png)

-----

### 對應講義 :  [20200717-2_Model & Seeding.pdf](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AACr_WGrcbxJCQAkb9trTx-pa/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200717-2_Model+%26+Seeding.pdf&subfolder_nav_tracking=1)

### Model :


![](https://i.imgur.com/iZo9MFr.png)

畫面 :

![](https://i.imgur.com/RdDg9uM.png)

Post Model 強制指定在 posts 的資料表

![](https://i.imgur.com/iHEUsRV.png)

### Seeder

![](https://i.imgur.com/e7QkFBk.png)

檔案位置 :

![](https://i.imgur.com/q7oS5ri.png)

內容 :

![](https://i.imgur.com/YfVy9ac.png)

小提醒 :

跟 Migration 的差別

up()
down()

### PostSeeder.php 

Post Model 來新增 posts 資料表的內容

![](https://i.imgur.com/YFa4iRf.png)

### DatabaseSeeder.php 作用

去呼叫其他的Seeder 檔

![](https://i.imgur.com/UJNk1mZ.png)

### artisan db:seed

![](https://i.imgur.com/xZHrR4N.png)

posts 資料表新增資料

![](https://i.imgur.com/6V8XdUL.png)


做多筆資料

使用 foreach() 

![](https://i.imgur.com/2zedhJT.png)

再執行 artisan db:seed 

![](https://i.imgur.com/KqnAYu7.png)

畫面 :

![](https://i.imgur.com/kllw5HC.png)

### 讓 seeder 更好

### [php faker](https://github.com/fzaninotto/Faker)

### [php carbon](https://carbon.nesbot.com/docs/)

### 產生未來時間 


### 產生過去時間~現在時間

### 產生中文faker

![](https://i.imgur.com/ZPrFPJi.png)

畫面 :

![](https://i.imgur.com/8dkg00l.png)

### 以上這是後端的教學
-----

### 開始後端結合了

把 [20200717-templates.zip](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AAAAT7cHBuq7kDt2PMt7yOM_a/%E7%B7%B4%E7%BF%92%E7%B4%A0%E6%9D%90?dl=0&preview=20200717-templates.zip&subfolder_nav_tracking=1) 的資料夾內容複製到現有的專案

畫面 :

http://localhost:8000/admin

![](https://i.imgur.com/Ljq8nW1.png)

### 對應講義 [20200717-4_CRUD.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200717-4_CRUD.pdf&subfolder_nav_tracking=1)

### 建立時間遞減

![](https://i.imgur.com/TX0OxiU.png)


![](https://i.imgur.com/cHtvEKo.png)
                                                                                                                                                         
### 表單的資料送出去 :

![](https://i.imgur.com/6A3RRtc.png)






### CSRF : 

![](https://i.imgur.com/N4EraiU.png)

### create 表單上新增的標題、內容

$request  -> except()
回傳一個陣列

![](https://i.imgur.com/WvB7QMB.png)

加入至資料表的內容?

![](https://i.imgur.com/hfbaCqz.png)

畫面 :
![](https://i.imgur.com/VZQOXF0.png)

###  遞減

跳轉至文章列面

![](https://i.imgur.com/BWesDQF.png)





### edit 



![](https://i.imgur.com/bBAVnW3.png)


### update

![](https://i.imgur.com/2ccGM3j.png)


![](https://i.imgur.com/32mn3tX.png)



### delete 

![](https://i.imgur.com/mVlGZWi.png)

![](https://i.imgur.com/r7GM8Ta.png)


![](https://i.imgur.com/q0laHAJ.png)





------

### 對應講義 : [20200717-6_升級指南.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200717-6_%E5%8D%87%E7%B4%9A%E6%8C%87%E5%8D%97.pdf&subfolder_nav_tracking=1)