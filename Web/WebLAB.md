## [Web] Kobe System	[20]

先查看 robots.txt 會發現應該是 flag 在的位置

直接連過去看會出現 ``只允許管理者`` 

修改 http header X-Forwarded-For 偽造來源 IP 為 ``127.0.0.1`` 

cookie 部分看起來應該是 base64 解出來是個 QRcode

QRcode 的內容為 ``{isAdmin:false}`` 把 ``flase`` 改成 ``true`` 重新做一個 QRcode 再用 base64 加密

這樣再回去看應該可以得到 Flag 了 
