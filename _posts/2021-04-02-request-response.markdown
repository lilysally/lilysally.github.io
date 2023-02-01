---
layout: post
title:  "Client Request, Server Response"
date:   2021-04-21 14:00:36 +0800
categories: jekyll update
---

## Client 與 Server 之間的溝通 : HTTP 協定

###  Client 與 Server : Request/Response cycle - http 協定


![](https://i.imgur.com/6X6yufD.png)

### Response Body -常見是JSON格式

Request Format
根據 HTTP 規範，伺服器端和客戶端進行請求與回應時，會使用定義明確的請求格式 (request format) 和回應格式 (response format)。

Request format 指的是，客戶端需要使用特定的 HTTP 動詞，對 URL 發出請求。Rails 採用的 RESTful 風格就是一種 request format。

Response Format
Response format 是指伺服器端回應時採用的資料格式，可能會是：XML、JSON、Protocol Buffers、Thrift、YAML 等等。

https://tw.alphacamp.co/blog/api-introduction-understand-web-api-http-json

### HTTP Method

https://www.dropbox.com/sh/smckyemt1i82les/AADoUR6gB6E6Zu7jQe64svUba/20190718_Laravel%20API%E5%8F%8ASSO%E8%AA%B2%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190718-2_HTTP.pdf&subfolder_nav_tracking=1

### HTTP Status Code

[MDN HTTP 狀態碼](https://developer.mozilla.org/zh-TW/docs/Web/HTTP/Status)
[HTTP Cats](https://http.cat/)

### API是甚麼?
API 全名：Application Programming Interface，譯為「應用程式介面」，也就是「應用程式對外開放的介面」。
作用：開發者可以透過 API 去使用其他人撰寫的應用程式。

### Web API

https://ihower.tw/cs/web-apis.html

https://lighthouse.alphacamp.co/courses/33/units/5247


### API 網站列表

https://github.com/hsiangfeng/APIList

### CROS

https://www.youtube.com/watch?v=Md9wxO6BU_c&ab_channel=%E6%B2%88%E5%BC%98%E5%93%B2

https://medium.com/jass-note/%E5%89%8D%E7%AB%AF%E7%AD%86%E8%A8%98-%E9%97%9C%E6%96%BCcors-%E7%9A%84%E9%82%A3%E4%BA%9B%E4%BA%8B%E5%85%92-f282c6d5c64f


使用跨域代理伺服器
在網址前面加 https://cors-anywhere.herokuapp.com/


成功

https://cors-anywhere.herokuapp.com/https://www.twse.com.tw/exchangeReport/STOCK_DAY_AVG?response=json&date=20200717&stockNo=2330&_=1594955758180



### JSON Server

### OAuth 2.0

沒有 OAuth 2.0 已經不能算是 API，而且要結合 JSON Web Tokens (JWTs) for OAuth 2.0，別再像舊時代以為自己處理請求跟回應就說是 Web API。

### RESTful API

https://www.youtube.com/watch?v=gHCB0sd47Is&ab_channel=%E6%B2%88%E5%BC%98%E5%93%B2

* REST  ( REpresentational State Transfer ) 具象狀態傳輸

來自Roy Thomas Fielding於2000年在其論文內提出的一種軟體架構風格，其概念結合了HTTP與URL兩種協定，以及如何運用於網路軟體架構設計。其特色在於以URL定位資源，並根據HTTP內容指示操作動作與回應訊息。目前主流的網路服務實現方案裡，因為REST相較之下更加簡潔，因此越來越多的網路服務採用REST風格設計和實現。通常一個符合REST實作方式的網路服務，就稱之為RESTful網路服務。

![](https://i.imgur.com/UzjoKGR.png)

#### 出處 : [RESTful API.pdf](https://www.dropbox.com/sh/smckyemt1i82les/AADoUR6gB6E6Zu7jQe64svUba/20190718_Laravel%20API%E5%8F%8ASSO%E8%AA%B2%E7%A8%8B/%E6%8A%95%E5%BD%B1%E7%89%87?dl=0&preview=20190719-1_RESTful+API.pdf&subfolder_nav_tracking=1)

---
### 同步請求 v.s. 非同步請求

### 同步請求 (Synchronous request)： 

![](https://i.imgur.com/5KKczsj.png)

客戶端 (client) 對伺服器端 (server) 送出 request ，並且在收到伺服器端的 response 之後才會繼續下一步的動作，等待的期間無法處理其他事情。這個作法並不理想，因為通常伺服器端的運算速度比本地電腦慢上好幾倍。
### 非同步請求 (Asynchronous request)：

![](https://i.imgur.com/nOCd3B4.png)


客戶端 (client) 對伺服器端 (server) 送出 request 之後，不需要等待結果，仍可以持續處理其他事情，甚至繼續送出其他 request。Responese 傳回之後，就被融合進當下頁面或應用中。

> 因為用 Ajax 技術發送的是非同步請求，所以「等待回應」期間還能送出新的請求
如果是同步請求，「等待回應」的期間不能做任何事情
向第三方伺服器請求回應時，由於你無法掌握伺服器回應的速度，運用非同步請求能避免使用者體驗到空白的等待時間

That's correct. 選項 2, 3, 4 描述了 Ajax 非同步請求的特色，如果是同步請求，你會需要等到伺服器回傳資料以後，才能發出新的請求，因此運用 Ajax 的使用者體驗比較好。

### Ajax 實現非同步請求 (Asynchronous Request)


在非同步請求 (Asynchronous request) 還沒被開發之前，如果我們要瀏覽一則留言，就必須向 Server 重新 request 一個完整的頁面。等待頁面切換的這段時間畫面往往會卡住不動，直到接收 response，才會重新渲染 (render) 畫面。

而 Ajax 技術的出現，讓瀏覽器可以向 Server 請求資料而不需費時等待。當瀏覽器接收到 response 之後，新的內容就會即時地添入原本網頁。這也是為什麼當我們瀏覽 Facebook、Twitter 內容時，不會看見整個網頁一直重新整理。

最早期的 Ajax 會利用一個 XMLHttpRequest 物件 (簡稱為 XHR ) 來實作，類似這樣：

```
function reqListener () {
  console.log(this.responseText);
}

var oReq = new XMLHttpRequest();
oReq.addEventListener('load', reqListener);
oReq.open('GET', 'http://www.example.org/example.txt');
oReq.send();
```

由於 XHR 使用起來很麻煩，所以實務上很少直接使用原生的 XMLHttpRequest。取而代之的方法有很多種，過去較流行的是 jQuery 的 $.ajax()，然而在 JavaScript 日趨成熟之後，許多新的替代方案應運而生，例如 HTML5 提供了 Fetch API，而我們使用的 axios 是一個非常受歡迎的 JavaScript 函式庫，他有許多重要功能如：

```
1.廣泛的瀏覽器支持
2.可支援 Node.js 從後端發送的 Http request，這意味著 axios 可以兼用於前端與後端專案。
3.直接將回應的 JSON 資料轉換成 JavaScript 的 Object，這十分方便！
```
### axios 串接 api

https://github.com/axios/axios


----

### 網頁渲染


DOM -> CSSOM -> Render Tree -> Layout -> Paint 

![](https://i.imgur.com/BQEWGw2.png)


連結: [網頁渲染的流程](https://medium.com/%E7%A2%BC%E8%BE%B2%E8%83%8C%E5%8C%85%E5%AE%A2/%E7%B6%B2%E9%A0%81%E6%B8%B2%E6%9F%93%E7%9A%84%E6%B5%81%E7%A8%8B-5c0f1430d46e) 