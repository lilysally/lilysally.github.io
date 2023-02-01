---
layout: post
title:  "Laravel工作坊Day1"
date:   2020-07-10 14:00:36 +0800
categories: jekyll update
---


# Day1

## Day2 筆記 : [20200710-17_Laravel 工作坊](https://hackmd.io/593qWvQYQHmaTiCTPw03cA)

### 對應講義 : [20200710-1_環境安裝與建置.pdf](https://www.dropbox.com/s/6ej3vfis6woatnn/20200710-1_%E7%92%B0%E5%A2%83%E5%AE%89%E8%A3%9D%E8%88%87%E5%BB%BA%E7%BD%AE.pdf?dl=0)

### 網站環境建置組合:
是Web application stacks的一種，也就是一組綁在一起來運行動態網站或伺服器的開源軟體。
#### 架構:作業系統(operating system)、網頁伺服器(web server)、資料庫伺服器(database server)、程式語言(programming language)。

常見開源軟體種類:
* LAMP (Linux + Apache + MySQL + PHP) 
* WAMP (Windows + Apache + MySQL + PHP) 
* MAMP (Mac OS + Apache + MySQL + PHP)

PHP、Apache、資料庫伺服器合作原理 :
![](https://i.imgur.com/f04mxt0.png)

[圖檔](https://www.dropbox.com/home/Laravel?preview=laravel.pptx)

#### [HTTP 狀態碼](https://developer.mozilla.org/zh-TW/docs/Web/HTTP/Status?fbclid=IwAR3R8ETVWhvmdtc-C13EAmxXtK_BFUJq2u-6IuAXD4IqCk3pNwFHiDiXaB0)

使用者透過PHP存取資料庫伺服器內容的流程:
* 1.使用者向Apache要求PHP相關網頁(.php)。
* 2.當Apache收到這個要求，經判斷，把此要求轉交給PHP直譯器負責。
* 3.PHP直譯器解譯此網頁的PHP語法，當遇到資料庫相關的函式，則把Request間接傳遞給資料庫伺服器。
* 4.資料庫伺服器把所要求的結果反傳回PHP 。
* 5.PHP直譯器把此結果包裝成Apache看得懂的HTML語法，後傳回給Apache。
* 6.Apache把此結果(已被PHP處理成HTML)傳回給使用者的browser。

Laravel 運行環境與建置需要 :
* 運行環境 : 網頁伺服器、PHP直譯器、資料庫
* 開發工具 : 程式編輯器、版本控制系統、指令執行工具、資料庫操作 adminer

### 免安裝可攜的 Laravel 開發環境 : [wagon](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AACNIIhKNzEke6H5h_qIYZvma/%E8%BB%9F%E9%AB%94/wagon-release-1.5.0.exe?dl=0)
#### wagon 整合了 cmder、git、UwAmp、composer
cmder為PHP CLI (PHP Command line interface)

### Cmder 的使用 :
![](https://i.imgur.com/SXmaaxJ.png)
* [UNIX指令](https://cscc.cs.nctu.edu.tw/unix-basic-commands)

git 為版本控制系統
UwAmp 開啟Apache與MySQL服務及設定PHP Version
composer為PHP的套件管理工具

### 進入PHPMyAdmin :
(1) 在網址列輸入 /mysql 
![](https://i.imgur.com/CdlAHe1.png)
(2) 在 UwAmp 介面上Tools 點 PHPMyAdmin
![](https://i.imgur.com/Y5B3vi0.png)
### 登入PHPMyAdmin :
* 輸入伺服器的主機位址:連接埠(hostname:port)
* 輸入帳號、密碼
* 輸入資料庫名稱
# 換成wagon 1.5.1 ， 因為PHP為7.3版
( 藍色框框:說明帳號、密碼預設都為root ，下面可修改帳密)
![](https://i.imgur.com/E1QOy0T.png)

![](https://i.imgur.com/wV8RREG.png)


 

### 程式編輯器軟體: [PhpStorm](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AAC-rKG0ZaLbhQe5rdGmPFd5a/%E8%BB%9F%E9%AB%94/PhpStorm-2020.1.2.exe?dl=0)
內建很好的PHP IDE

[介紹PhpStorm — 以 Laravel 開發為例](https://medium.com/@shengyou/full-in-love-with-phpstorm-f6d484109978)

### 後端語言的套件管理工具 : 
* Node.js : npm、Yarn
* Ruby : gem
* PHP : Composer、Pear、Pecl

### 語意化版本(Semantic Versioning) :
                  X(主版號).Y(次版號).Z(修訂號)
版號遞增規則如下：
* 主版號：當你做了不相容的 API 修改
* 次版號：當你做了向下相容的功能性新增
* 修訂號：當你做了向下相容的問題修正

### 版本號演進 :
![](https://i.imgur.com/Y7dMxSb.png)

![](https://i.imgur.com/x1EExZs.png) 

至於 Laravel 的版本號沒有遵循上面是因為，作者前面沒有按照語意化版本的規則排，換版的時候也比較不會在乎更新維護上的差別，後來有按照規則跑，後面頂多就只有小編號跟修正號的差異而已，不會到有以前換號就像是重大更新那樣，所以他才會把小編號開始的數字直接省略為'X'，因為在使用說明上同一版本不會有太大影響。

### PHP推薦標準 : [PHP-FIG](https://www.php-fig.org/)
* PSR標準規範: 目前最新為PSR-4
### PHP的套件管理中心 : [Packagist](https://packagist.org/)

--------
### 對應講義 : [20200710-2_初階版本管理.pdf](https://www.dropbox.com/s/7viugctbkxa2rkx/20200710-2_%E5%88%9D%E9%9A%8E%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86.pdf?dl=0)

### 防止防火牆阻擋 :
剛開始用PhpStorm時，點Event Log之後出現的視窗，按Fix..來防止防火牆阻擋

![](https://i.imgur.com/cDDkj9H.png)

按 Configure Automatically按鈕，就完成了

![](https://i.imgur.com/I5jgytd.png)

### 設定git.exe路徑 :

git/ cmd下的 git.exe
 
![](https://i.imgur.com/JZkTFfU.png)

選擇完git路徑後，按 Test 按鈕，成功則會出現版本號

![](https://i.imgur.com/w0FKNui.png)

### 初始化專案 (git init):
![](https://i.imgur.com/gIXySos.png)

在左下角出現綠色框框訊息，
顯示 Created Git repository in 目前專案位置

![](https://i.imgur.com/GMUbaBR.png)

### 這為 PhpStorm 內建的 git 介面 :

![](https://i.imgur.com/UHjOGcK.png)

勾選 Use non-modal commit interface後，視窗會釘選在左邊

![](https://i.imgur.com/WMlNJ7c.png)

沒勾選，則出現在下面Git那的 Local Changes

![](https://i.imgur.com/Vv6YgUB.png)

這種git的操作比較麻煩，建議是放在左邊

### git add :
勾選動作為 git add

![](https://i.imgur.com/TlS7Vxv.png)

### git commit -m '訊息' : 
輸入Commit Message後， 按Commit 按鈕，完成git commit 動作

![](https://i.imgur.com/RmWSmNL.png)

#### Log:all視窗 :
在這，看到剛剛commit上去的紀錄

![](https://i.imgur.com/NZcaZdz.png)
### git log : 查看commit紀錄
### git status : 查詢當前狀態



### git commit 後，檔案上的列數旁顏色變化說明 :

* 綠色 : 新增
* 藍色 : 修改
* 灰色箭頭 : 刪除

![](https://i.imgur.com/Wg5j6d6.png)

### git diff :

看 git commit 前後的差異
![](https://i.imgur.com/pgXdT90.png)

Log:all視窗中，點選一筆commit紀錄後，右邊會出現檔案及commit message，點擊檔案2下後，則會開新視窗，就可以達到上方畫面效果
### show History : 

可查看多筆 git commit 完成的差異

![](https://i.imgur.com/yXX9Otd.png)

### 中階版本管理 : [20190125-2_中階版本管理.pdf](https://www.dropbox.com/s/7viugctbkxa2rkx/20200710-2_%E5%88%9D%E9%9A%8E%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86.pdf?dl=0)

-----
### 對應講義 : [20200710-4_Route 與 Controller.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200710-4_Route+%E8%88%87+Controller.pdf&subfolder_nav_tracking=1)


### Route : 

在 routes 資料夾下，選擇 web.php 
#因為應用於網頁


![](https://i.imgur.com/LisEyLq.png)

紅色框框為 Route::get() 對應的 PHP 語法

![](https://i.imgur.com/4q77HiK.png)

### 設定 Router 動作 : 

![](https://i.imgur.com/6ns45Y7.png)

### HTTP request method : get
get方法的參數意義，Route::get('網址','反應')
![](https://i.imgur.com/gR4vxdx.png)

### 設定 Router 反應 :

![](https://i.imgur.com/hXiTVKD.png)

### [PHP的 Http request methods 呈現方式](https://www.dropbox.com/sh/smckyemt1i82les/AADoUR6gB6E6Zu7jQe64svUba/20190718_Laravel%20API%E5%8F%8ASSO%E8%AA%B2%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190718-2_HTTP.pdf&subfolder_nav_tracking=1)

#### 反應 :
* 回傳字串

EX-1 :

在本機 (http://localhost:8000/) 下

![](https://i.imgur.com/sJfsLN4.png)

EX-2:

在/hello (http://localhost:8000/hello) 下

![](https://i.imgur.com/q5meFVy.png)

EX-3:

在/hello/index (http://localhost:8000/hello/index) 下


![](https://i.imgur.com/6ExJw3R.png)
#### 反應 :
* 回傳 view

跳至XXX.blade.php (MVC架構的V:View)
(XXX.blade.php來自於resources/views下)

EX-1:

在本機 (http://localhost:8000/)下，跳至 welcome.blade.php 

![](https://i.imgur.com/q4H13hX.png)

![](https://i.imgur.com/pLviNaw.png)

EX-2:

在/hello (http://localhost:8000/hello)下，跳至 hello.blade.php 

![](https://i.imgur.com/g7wrUh4.png)

![](https://i.imgur.com/Qa8BGa9.png)

EX-3:

在/hello/index (http://localhost:8000/hello/index)下，跳至 index.blade.php 

![](https://i.imgur.com/fp0cvnJ.png)

![](https://i.imgur.com/twwoIRQ.png)

#### 反應 :
* 跳轉頁面

EX:

routes/web.php

![](https://i.imgur.com/EvKueMO.png)

app/Http/Controllers/AlinkController.php

![](https://i.imgur.com/Q72KUpn.png)

![](https://i.imgur.com/uiwhszk.png)




噴錯誤 :

![](https://i.imgur.com/aFHH4t4.png)

改善方法 :

![](https://i.imgur.com/su9Ynjb.png)

to() 方法 :

dd() 函式 : 是開發過程中最常用的函式之一，可以印出送入的參數，並且暫停程式。

#### [redirect後接的方法](https://stackoverflow.com/questions/28642753/redirect-to-external-url-with-return-in-laravel)

![](https://i.imgur.com/kbgWNgi.png)

### Router 接收參數 :

![](https://i.imgur.com/Mi0mJgB.png)

#### 接收選擇性參數 : 
* 自行輸入參數 :

輸入 shengyou

![](https://i.imgur.com/rMgcRk7.png)

* 沒有輸入參數 :

name變數值，預設為Everybody



### Laravel 的 MVC 分工 :

![](https://i.imgur.com/zdxgkE1.png)

#### [MVC 架構演進 — 為什麼需要MVC](https://medium.com/@rayshih771012/mvc-%E6%9E%B6%E6%A7%8B%E6%BC%94%E9%80%B2-%E7%82%BA%E4%BB%80%E9%BA%BC%E9%9C%80%E8%A6%81mvc-d1a13aa687a0)

### Controller : 

避免都把程式邏輯寫在routes/web.php，太長也沒有分類，
所以利用 Controller檔來控制 Router(路徑)，
由他的method 來處理查詢(Model)、回傳頁面(View)、跳轉頁面(Redirect)。

### 產生 Controller 檔 : 

#### artisan make:controller

![](https://i.imgur.com/eIX1vCK.png)

Cmder 輸入 : artisan make:controller {nameController}
![](https://i.imgur.com/GHWdPqR.png)

成功建立 HomeController檔後，出現在  app/Http/Controllers 下

![](https://i.imgur.com/X4sIDh1.png)

#### RESTful :

* 簡單來說就是一個Http request method使用API的協定及回傳格式制式化，讓其他工程師維護的話能快速看懂某支API的用途，由工程師之間互相約定好的道德標準，讓程式碼維護起來會快速、方便、簡潔。

在發送 Http request 時通常都是使用  get 、 post 這兩種，但在 RESTful 協定下多了 put、patch、delete 這些method，主要是為了開發、維護方便及清楚。

在有遵守的狀況下，網址會是以下範例：

http://localhost/delete/5

這行清楚顯示，這是負責某資料刪除的API

http://localhost/patch

這行清楚顯示，這是負責修改資料的API

但實際上在運作 :
get和delete還是使用get來傳遞參數(從網址)，而其他的method還是使用post來傳遞參數(從request body)

### RESTful API講義 : [20190719-1_RESTful API.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AADoUR6gB6E6Zu7jQe64svUba/20190718_Laravel%20API%E5%8F%8ASSO%E8%AA%B2%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190719-1_RESTful+API.pdf&subfolder_nav_tracking=1)
### 將 Route 指向 Controller :

#### HTTP介紹 : [20190718-2_HTTP.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AADoUR6gB6E6Zu7jQe64svUba/20190718_Laravel%20API%E5%8F%8ASSO%E8%AA%B2%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190718-2_HTTP.pdf&subfolder_nav_tracking=1)
#### 示範步驟流程 (get 為例) :

在 web.php 的 get方法裡，第2個參數的 function 區塊剪下

![](https://i.imgur.com/1b51ZxV.png)

貼至 HomeController.php 的 Class 裡

![](https://i.imgur.com/QLZDbnd.png)

補上 function 名稱後，在 function 前加上 public

![](https://i.imgur.com/xHhLH24.png)

之後回到 web.php 頁面，get方法的第二個參數要補上東西

![](https://i.imgur.com/fnjdgZX.png)

輸入對應的 Controller檔@function name 

![](https://i.imgur.com/c8MxyDS.png)

完成在本機下，呈現的頁面(view) 為welcome.blade.php

![](https://i.imgur.com/bc6EtyD.png)

#### 設定4個Http request methods(get、post、patch、delete) 範例 :

![](https://i.imgur.com/Yxu5Nb5.png)

### Module :

module 連資料庫 

在 database/migrations 下

![](https://i.imgur.com/G2lFxCT.png)

詳細操作可參考 : 
[Laravel 5.8 會員註冊及登入系統API：Model & Controller](https://ithelp.ithome.com.tw/articles/10226796)



----
### 對應講義 : [20200710-3_初始 Laravel 專案.pdf](https://www.dropbox.com/s/l5af955ybb1df27/20200710-3_%E5%88%9D%E5%A7%8B%20Laravel%20%E5%B0%88%E6%A1%88.pdf?dl=0)
### 開啟wagon的Web預設畫面 :
![](https://i.imgur.com/zv83a3k.png)
![](https://i.imgur.com/yM5P6Oy.png)
### 修改wagon的Web預設畫面 :
![](https://i.imgur.com/C40t4Qu.png)

調整完，Apache Server會暫停

![](https://i.imgur.com/ohrZtF9.png)

啟動完，就可看到firstproject專案的 Web

![](https://i.imgur.com/MHEHTUw.png)
![](https://i.imgur.com/48OtKpa.png)
### 成功安裝Composer : 
輸入composer指令後，會出現composer版本號
![](https://i.imgur.com/kAkM0ce.png)

### 用 Composer 建立 laravel 專案 skeleton : 
輸入 
composer create-project laravel/laravel {專案名稱} --prefer-dist

![](https://i.imgur.com/kgkNS5W.png)

安裝完畢

![](https://i.imgur.com/DPOdahV.png)

### composer 的 create-project指令後的參數說明 :

![](https://i.imgur.com/htn8GCp.png)

### 使用 Laravel 的 Documnet Root :
要指向 /public

![](https://i.imgur.com/3rAwIcS.png)

Laravel 框架的Route才啟動成功

![](https://i.imgur.com/Px6muk6.png)
### public 資料夾 :
![](https://i.imgur.com/ZEB1YZ6.png)

![](https://i.imgur.com/1EhToSH.png)

### (重點) Laravel 目錄結構 :
![](https://i.imgur.com/FKw03rW.png)

### 修改預設的Laravel框架Web :
![](https://i.imgur.com/E1k1ibV.png)
![](https://i.imgur.com/PbTT6Db.png)

### composer.json
屬性值的意義 

![](https://i.imgur.com/I6tsmaR.png)



### 查看Laravel的版本號
(1) Cmder下輸入 artisan (artisan --version)

![](https://i.imgur.com/Q6IONLD.png)

(2)在 composer.json 下的 require 屬性裡的 laravel/framework

![](https://i.imgur.com/yU99fU0.png)

### 使用laravel其他的版本號 :
假如要使用6.0

![](https://i.imgur.com/n4vFmtI.png)

 Cmder下輸入 composer update 
 
![](https://i.imgur.com/20pU0ej.png)

composer.lock

![](https://i.imgur.com/E7nIV7t.png)
### .json和.lock差別 :
![](https://i.imgur.com/N6dBifA.png)

功用 : 

![](https://i.imgur.com/6lF02l4.png)

比較 :

![](https://i.imgur.com/LFpZQCK.png)

### namespace
*  解決不同人(或者是資料夾)使用同樣名稱的類別(Class)

EX:
取名一個叫做 Toy 的空間，在 namespace 後面的 Class 都將會被歸類在 Toy 底下

![](https://i.imgur.com/HiXls54.png)

匯入namespace，使用use語法 : use namespace \ Class name

![](https://i.imgur.com/z4cV3dE.png)

小提醒 : 

使符號閱讀性高、人性化的方法，
勾選 Enable font ligatures

![](https://i.imgur.com/5G1KjWS.png)

符號閱讀性高、人性化的種類 :

![](https://i.imgur.com/Ws5L2ai.png)

結果 :

![](https://i.imgur.com/GPasjzN.png)

### Laravel 裡建立 Class :

規則:
* 為 namespace 建立一個 以他為名的資料夾
* 使用 namespace 的檔案，檔案命名為 Class 的名稱
* namespace 裡的 Class 檔案，放至他的資料夾下

示範流程 :

使用 namespace 的 Class name 為 Car
( Class name 的開頭必須為大寫)

![](https://i.imgur.com/DdvscqE.png)

修改檔案名稱

![](https://i.imgur.com/lGUMNjH.png)

修改完後，在Car.php 旁會出現藍色圓圈的C，
代表這檔案為Class (類別 )

![](https://i.imgur.com/4hN5G5p.png)

namespace 為 Toy，所以新增以 Toy 為名的資料夾

![](https://i.imgur.com/BOD2Wr7.png)

之後在把 Car.php 移至 Toy 資料夾下

![](https://i.imgur.com/PfPvikf.png)

這樣也使 use 後的路徑，比較直覺

![](https://i.imgur.com/iDZpPEk.png)

### PHP-FIG 制定的套件開發標準 : [PSR-4](https://docs.laravel-dojo.com/fig-standards/master/PSR-4)

在 PSR-4 的 Autoloader 規格中，會自動載入 namespace

[( 詳細 ) PSR-4的自動載入規格](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader-examples.md)

在composer.json中有PSR-4規格

![](https://i.imgur.com/71EbRx6.png)

### Laravel 專屬的指令列工具 : artisan

輸入 artisan 指令，顯示Laravel框架的版本號及 artisan 可用的指令

![](https://i.imgur.com/GYVrQEV.png)

假如每個專案內的Laravel版本號不同，就會有不同的artisan 

![](https://i.imgur.com/FyAZBIO.png)

-----

### 對應講義 : [20200710-5_Blade 樣板引擎.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AAC6MiqSP5NPaThj4okBlBH8a/20200710-PHP%E9%96%8B%E7%99%BC%E6%B5%81%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20200710-5_Blade+%E6%A8%A3%E6%9D%BF%E5%BC%95%E6%93%8E.pdf&subfolder_nav_tracking=1)

### 義大利麵( 米粉 ) 程式碼
![](https://i.imgur.com/gXdFIMA.png)

### Laravel 的 MVC 之 View 是甚麼:

![](https://i.imgur.com/054UNag.png)

### Laravel 的樣板引擎 :

![](https://i.imgur.com/XzbyodV.png)

### 啟動 Blade 解析器 : 

![](https://i.imgur.com/OzMCZpf.png)

### 常見的網頁排版 :

![](https://i.imgur.com/8unutyZ.png)

### 方便管理網頁共用問題 :

* 利用 Blade 語法

#### 示範流程 (以 Blog Home 為例 ) :

搜尋 startbootstrap : [startbootstrap-Blog](https://startbootstrap.com/templates/)，進去 Blog Home 裡面
![](https://i.imgur.com/475bXsd.png)
按 Free Download 下載，或是直接點擊下方練習素材

![](https://i.imgur.com/5xR5vd2.png)

練習素材:
* [Blog Home](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AACOT6_II8sjrQT-gaB9FK6oa/%E7%B7%B4%E7%BF%92%E7%B4%A0%E6%9D%90/startbootstrap-blog-home-gh-pages.zip?dl=0)

下載完 Blog Home後，解壓開啟他的資料夾
 
#### 把 css 相關的丟至 blog 專案下的 public/css 下


* \css

![](https://i.imgur.com/DFJTZR1.png)

* \vendor\bootstrap\css

![](https://i.imgur.com/5RQHVxv.png)

#### 把 js 相關的丟至 blog 專案下的 public/js 下

* \vendor\bootstrap\js

![](https://i.imgur.com/Fho32EV.png)

* \vendor\jquery

![](https://i.imgur.com/D8rzoY5.png)

public/css；public/js 完成畫面 :

![](https://i.imgur.com/WZCge24.png)

在 resources/views 下 新增 blog 資料夾

![](https://i.imgur.com/7WLnBYf.png)

#### 把 index.html 丟至 blog 資料夾下後

![](https://i.imgur.com/lpyY4i8.png)

#### 改名成 index.blade.php

![](https://i.imgur.com/R6cHSlj.png)

#### 在 /hello/index 下，畫面連至 blog/index.blade.php 

![](https://i.imgur.com/LyiO4zz.png)

在 /hello/index (http://localhost:8000/hello/index)下的畫面 :

![](https://i.imgur.com/QRSAh2A.png)

![](https://i.imgur.com/H9TDPgb.png)


### 解決css、js 沒吃到問題 : [asset()](https://laravel.com/docs/7.x/helpers#method-asset)

#### asset()是Laravel helpers函數，其功能就是導向專案資料夾public
#### {{}} 簡化PHP標籤及一些語法

小提醒 : 

{{}} 會跟 Vue(前端JS框架)顯示語法衝到，可以利用 @ 跳脫
```
<h1>Laravel</h1>

{{-- 利用 @ 跳脫，Blade 並不會處理這段，而是直接完整顯示 {{ name }} 在 HTML 中 --}}
Hello, @{{ name }}.
```

原本 : 

```
<link rel="stylesheet" href="<?php echo asset('css/app.css') ?>">
```
使用 {{}} ：
```
<link rel="stylesheet" href="{{ asset('css/app.css') }}">
```

* 原先 css 路徑 :

![](https://i.imgur.com/G1VlCsw.png)

使用 asset() 語法修法 css path :

![](https://i.imgur.com/K7hTMo6.png)

* 原先 js 路徑 :

![](https://i.imgur.com/7WPGwlU.png)

使用 asset() 語法修法 js path :

![](https://i.imgur.com/TrB3Rit.png)

吃到 css 及 js 完成畫面 :

![](https://i.imgur.com/owuq7Sg.png)

### 開始拆解區塊 :

在 resources/views 下 新增 layouts 資料夾

![](https://i.imgur.com/h96y47G.png)

再 layouts 資料夾下，新增 partials 資料夾
![](https://i.imgur.com/ChNYCgS.png)

#### 拆解 Navigation 區塊 :

* 在 partials 資料夾下，新增 navigation.blade.php

![](https://i.imgur.com/LEyh85t.png)

* 在 blog/index.blade.php 裡，
把 Navigation 區塊剪下至 navigation.blade.php


![](https://i.imgur.com/k3ssxNk.png)

完成畫面 :

![](https://i.imgur.com/7QdU9C4.png)

#### 拆解 Footer 區塊 :

* 在 partials 資料夾下，新增 footer.blade.php

![](https://i.imgur.com/yXvAWCa.png)

* 在 blog/index.blade.php 裡，
把 Footer 區塊剪下至 footer.blade.php

![](https://i.imgur.com/RttsrUj.png)

完成畫面 :

![](https://i.imgur.com/mmEWsv2.png)


#### 拆解 Sidebar 區塊 :

* 在 partials 資料夾下，新增 sidebar.blade.php

![](https://i.imgur.com/zlE8GUQ.png)

* 在 blog/index.blade.php 裡，
把 Sidebar 區塊(紅色框框)剪下至 sidebar.blade.php

![](https://i.imgur.com/AsyeD9O.png)

完成畫面 :

![](https://i.imgur.com/kDyLIqS.png)

### Blade 樣板引擎 : 

在 layouts 資料夾下，新增 master.blade.php，
#### master.blade.php 為 父view (子views繼承來自他)

![](https://i.imgur.com/jEazDlX.png)

master.blade.php 的檔案階層跟 partials 一樣

![](https://i.imgur.com/SUEzw2L.png)

把 blog/index.blade.php 內容剪下至 master.blade.php

![](https://i.imgur.com/6zGPZnP.png)

### 使用 @include 引入view :

* navigation.blade.php 

![](https://i.imgur.com/DFOhPwT.png)

* footer.blade.php 

![](https://i.imgur.com/4ism9kc.png)


把這段剪下，貼至 blog/index.blade.php

![](https://i.imgur.com/bx2wlLl.png)

畫面 :

![](https://i.imgur.com/kOSBiYS.png)

### 使用 @yield 用來顯示給定區塊的內容 :
在 master.blade.php 輸入 @yield

![](https://i.imgur.com/oI4usu2.png)

### 使用 @extends 指定子頁面應該「繼承」哪一個view :

在 blog/index.blade.php下，輸入 @extends

![](https://i.imgur.com/bxY2eDb.png)

在 Page Content 區塊加入 sidebar.blade.php

![](https://i.imgur.com/MPETshQ.png)

### 使用 @section 定義內容區塊 :
在 Page Content 區塊 前後 加入@section

![](https://i.imgur.com/NtNAq01.png)

結果畫面 :

![](https://i.imgur.com/cj3DMJy.png)

### show.blade.php

![](https://i.imgur.com/Yi1rjvC.png)

把 index.blade.php 內容複製

![](https://i.imgur.com/SFYhkKy.png)

貼上後，修改 @section 與 @endsection 中間的內容，改為 SHOW!!!

![](https://i.imgur.com/dqEFgsl.png)

在 /hello/show (http://localhost:8000/hello/index) 下 的 Route，指向 show.blade.php 頁面

![](https://i.imgur.com/FiTi1m8.png)

畫面 : 

![](https://i.imgur.com/ojEeXzQ.png)

----
最終結果檔:
* [blog.zip](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AACbpAywbsmI_hWvSD5SrX1ta/%E7%AF%84%E4%BE%8B%E6%AA%94?dl=0&preview=blog.zip&subfolder_nav_tracking=1)
---
作業檔 :
* [Blog Post](https://www.dropbox.com/sh/7ire7s50qgaf3qp/AABFFKtI1FnyzbQNmyeyFgg7a/%E7%B7%B4%E7%BF%92%E7%B4%A0%E6%9D%90/startbootstrap-blog-post-gh-pages.zip?dl=0)


### 作業要求 : 

![](https://i.imgur.com/90B67sn.png)

# (圖片要修改)
 
利用 Blade 樣板引擎，製作

* /
* /blog
* /blog/{id}

---
### 參考資料 :
* [Web application stacks](https://ithelp.ithome.com.tw/articles/10215686)
* [PHP、Apache、MySQL合作原理](https://www.cyut.edu.tw/~hcchu/course/MAN_95A/MANCh10.pdf)
* [wagon介紹](https://github.com/laravel-dojo/wagon)
* [安裝/設定 PhpStorm](https://ithelp.ithome.com.tw/articles/10195317)
* [語意化版本](https://semver.org/lang/zh-TW/)
* [Laravel 文件瀏覽器](https://medium.com/laraveldojo/laravel-dojo-monthly-challenge-no1-200ff7d0f02b)
* [修改 Laravel 版本號](https://ithelp.ithome.com.tw/articles/10213570)
* [Laravel 5.8 會員註冊及登入系統API：Model & Controller](https://ithelp.ithome.com.tw/articles/10226796)
* [Laravel Helpers-dd()](https://ithelp.ithome.com.tw/m/articles/10222233)
* [Composer 從入門到實戰](https://www.slideshare.net/shengyou/composer-fromscratch?ref=https://cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.slideshare.net%2Fslideshow%2Fembed_code%2Fkey%2F2vT5bqPgWM7mhr&url=http%3A%2F%2Fwww.slideshare.net%2Fshengyou%2Fcomposer-fromscratch&image=http%3A%2F%2Fcdn.slidesharecdn.com%2Fss_thumbnails%2Fcomposer-from-scratch-160923040723-thumbnail-4.jpg%3Fcb%3D1475337195&key=d04bfffea46d4aeda930ec88cc64b87c&type=text%2Fhtml&schema=slideshare)
* [20190718-1_Composer 套件管理.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AADoUR6gB6E6Zu7jQe64svUba/20190718_Laravel%20API%E5%8F%8ASSO%E8%AA%B2%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190718-1_Composer+%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86.pdf&subfolder_nav_tracking=1)
* [php – namespace 命名空間教學介紹](http://jsnwork.kiiuo.com/archives/1947/1947/)
* [asset 語法與 {{}} 介紹](https://ithelp.ithome.com.tw/articles/10194132)
* [Laravel 5.2 Blade 樣板引擎語法介紹](https://laravel.tw/docs/5.2/blade#defining-a-layout)
* [Laravel 5.7 Views and Blade](https://blog.johnsonlu.org/laravel-blade-views/)