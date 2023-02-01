---
layout: post
title:  "大學專題-開始比對&重新開始"
date:   2021-09-16 14:00:36 +0800
categories: jekyll update
---

# Page04.html&page5.php


* 開始比對 -> execute.php

// 點擊(onclick)觸發 file_upload1() 跟 file_upload2()
// 同步請求，處理完檔案上傳，才會跳到upload.php
https://hackmd.io/tZXUUBYsTxauta7BRBJcJQ
// $_FILES["file"]["error"](文件上傳成功) == 0 跟檔案類型正確，才會上傳


> $_FILES["file"]["error"] == 0 (文件上傳成功)
> $_FILES["file"]["error"] == 4 (没有文件被上傳)
https://www.php.net/manual/zh/features.file-upload.errors.php


* 條件 : 沒有點擊檔案上傳(没有文件被上傳?)

javascript如何判断一个事件是否执行完成还是正在执行中？？
https://zhidao.baidu.com/question/359302736.html

->click(點擊)事件去執行 file_upload1() 跟 file_upload2()，故利用JS變數去偵測是否執行此事件

file_upload1() 跟 file_upload2() 的 變數(偵測"上傳檔案"按鈕)要怎麼讀取??

-> (X) 用函數傳值



Q : 考慮JS變數存活性? 還是用PHP變數去紀錄?(JS變數傳給PHP?)




----



```
//execute.php
<?php
session_start();
set_time_limit(0);//防止執行超時、解除限制（原本是120s就會掛掉）
// echo $_SESSION['path'][0];

// $params = "Dog,Cat,Horse"; #傳值給 python 接收  
// $params1 = "test";
// $cmd = "activate punch && python test.py "; //末尾要加一個空格
// passthru($cmd.$path1.$path2);//等同於命令`python python.py 引數`，並接收列印出來的資訊

// header("location: loading.html");

// $path1 = "E:/topic/video/myvideo/開合跳1.mp4";
// $path2 = "E:/topic/video/myvideo/開合跳1.mp4";




$path1 = $_SESSION['path1'];
$path2 = $_SESSION['path2'];

// echo $path1;echo "<br>";
// echo $path2;echo "<br>";

exec ( "activate boxing && python rewrite.py  $path1 $path2 ",$log,$status);//傳值成功
// exec ("activate boxing python test.py ",$log,$status);//傳值成功
echo print_r($log);
echo "<br>";
echo $status;

if ($status == 0) {
    header("location: ../webpage/page5.php");
}
?>
```



* 重新開始 -> ~~Page04.html~~  restart.php

//清除 session 
https://www.webtech.tw/info.php?tid=33

```
<?php
include('../php/execute.php');
unset($_SESSION['path1']);
unset($_SESSION['path2']);
session_destroy();
header("location: ../webpage/Page04.html");

?>
```

有要清除cookie??