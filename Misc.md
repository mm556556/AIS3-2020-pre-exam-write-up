## **🐧Misc**

### **💤Piquero (347 Solves ; point: 100)**
    I can’t see the flag. Where is it?

![](https://i.imgur.com/haDtGI4.jpg)

餵給狗吃發現在 BambooFox CTF 曾經出過類的題目，
但其實也不難發現是點字，慢慢查表很快就能得到 flag 。



### **🐥Karuego (245 Solves ; point: 100)**
    Students who fail to summon will be dropped out.


似乎是考古題，題目給了一張圖片

![](https://i.imgur.com/yv3rUgg.jpg)

先用 binwalk 拆拆看

![](https://i.imgur.com/Haisbkf.png)

裡面藏了一份加密過的 zip 檔，且發現裡面有兩張圖片，把其中一張3a66fa5887bcb740438f1fb49f78569cb56e9233_hq.jpg 餵給狗吃後發現網路上已經有一張一模一樣的圖片了，所以這時就能使用 **pkcrack 已知明文攻擊**破解zip檔。

查了網路上的指令：
```
C :要破解的目標文件
c ：破解文件中的明文文件的名字
P ：壓縮後的明文文件
p : 壓縮的明文文件中明文文件的名字
d : 最後得到的沒有加密的zip文件
```
把剛剛 google 到的那張圖片壓縮成 zip 檔。
(這裡我有把從題目得到的檔案重新命名過，所以檔名可能跟原本得到的檔案會有差)

![](https://i.imgur.com/IQb3AGC.png)

之後拿到解密過後的壓縮 result.zip ，unzip 後就能打開另一張被加密過的圖片，和其中的 flag 。

![](https://i.imgur.com/WYCNCOr.jpg)
