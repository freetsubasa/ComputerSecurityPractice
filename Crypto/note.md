## [Crypto] Crypto 1 [10]

``ONZOBBSBK{EHOLVFORGGREGUNACLGUBAEVTUG}``

凱撒加密，``ONZOBBSBK`` 對應到的是 ``BAMBOOFOX``


## [Crypto] Crypto 2 [20]

A XOR B = C

C XOR B = A

掌握這個就可以拿題目給的跟產生出來的 key 推回去得到 flag

```
#!/usr/bin/env ruby
Key = [133, 195, 108, 150, 68, 57, 67, 167, 215, 209, 65, 93, 59, 127, 229, 177, 63, 179, 110, 232, 216, 129, 74, 255, 80, 165, 109, 67, 188, 38, 216, 236, 171, 95]

gg  = []
final = []

seed = 0
m = 256
a = 1103515245
c = 12345

Key.each do |flag|
	seed = ((a * seed - c) % m)
	gg << seed
end

Key.zip(gg).map do |a,b|
	t= a ^ b
	final << t
end

p final.pack 'c*'

```


## [Crypto] Crypto 4 Practice [10]

把 ``BAMBOOFOX{The_flag_in_int}`` 轉成 hex 前面加個 0x 丟進 irb 裡面就結束了


## [Crypto] Crypto 5 Practice [10]

把 ``28679783438969529831390483614607539261012`` 轉成字串

```
a = 28679783438969529831390483614607539261012.to_s 16
[a].pack('H*')
```






