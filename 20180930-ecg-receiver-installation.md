#  關於 ecg receiver 安裝在 raspberry pi 的說明
## 1.直接在終端機介面輸入：
```
npm install https://github.com/akiicat/ecg-receiver
```
安裝好的檔案會儲存在/home/pi/node_module/ecg-receiver下


# 關於開機自動執行 ecg receiver 的說明
## 1.先進入管理者模式(root)
在終端機中輸入：
`sudo su`
## 2.進入etc資料夾，然後編輯rc.local檔
1.在終端機輸入：
`cd /etc`
`vim rc.local`

2.編輯rc.local會出現以下畫面

![image alt](https://i.imgur.com/Vno2mqi.jpg)



可以看到有兩段我用來作測試的兩段程式碼
`echo "HI" >/tmp/hello`
`node /home/pi/test.js &`
以上區域所輸入的程式碼皆會在開機時自動執行
因此這時請也在
`exit 0`
上方輸入：
`sudo node /home/pi/node_modules/ecg-receiver/app.js`
儲存退出後，reboot即可執行

3.關於輸出檔的問題
開機執行的程式與一般直接從終端機執行的程式不同，
像是測試用的test.js中
![image alt](https://i.imgur.com/SABSILI.jpg)
輸出檔為test1.txt
如果沒有標明路徑，開機後不會生成txt檔在同一目錄下
(然而如果直接在終端機下執行可以)

