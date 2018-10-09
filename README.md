<pre>
cd ls grep 
find cp mv 
rm vim cat
mkdir touch history
</pre>

`cd ..    `
`cd ../../    `
`ls    `
  
go home    
    - `cd ~    `
make directory   
    - `mkdir    `
make file    
    - `touch      `
    - 如果檔案已存在，touch只會更新最後開啟時間    
  
  
## grep   
  
-regular expression搜尋    
-預設和google搜尋一樣    
    - `grep "test"`時，test123也會被搜尋到    
    - 可用-w參數    
        - `grep -w "test"`，就會只搜尋到test     
  
搜尋每個底下的資料夾    
    `grep -r "statdata"    `
  
顯示行數 -n (在debug時可以幫你快速找到錯誤)    
    `grep -n "main" test.js    `
  
顯示找到的次數 -c    
    `grep -c "main" test.js        `
  
在其他的指令下filter    
    `ifconfig | grep –w "RUNNING"    `  
    `find . –name "*.mp3" | grep –i JayZ | grep –vi "remix"  `
  
  
## find   
  
搜尋"這個目錄"底下的檔案，只顯示檔名和路徑  
`find . -name ereadium*  `  
> cmder不能用這個指令
  
## cp  
複製"這個目錄"底下的file1  
    `cp file1 file2  `
    複製目錄和所有檔案
    `sudo cp -r Resources/ /var/www/html/`  
    覆蓋已存在的檔案
    `sudo cp -rf Resources_2/200010 Resources/`
  
## mv  
移動file1到dir目錄  
`mv file1 dir  `
  
## rm  
remove  
    -f 強制移除  
    -i 移除前會詢問確認  
    -r recursive, 小心使用!  
  
## vim  
用vim打開  
`vim test.txt`  
    i  切換到編輯模式  
    esc 從編輯模式切換回指令模式  
        在指令模式下  
        :w 存檔  
        :q 離開  
        :q! 強制離開  
        gg 到最上面  
        G  到最下面  
  
## cat / more  
看檔案內容  
`cat test.txt`
-cat 顯示全部  
-more 一次顯示一整頁  
  
  
## history  
顯示執行過的命令  
  
  
## scp
上傳20003資料夾到遠端server  
-i  使用加密檔(xxx.pem)  
scp -ri \Users\cli\Downloads\wushka\Wushka_Dev.pem 200003\ ubuntu@ec2-13-211-158-9.ap-southeast-2.compute.amazonaws.com:  


-------------------
## Move whole folder from local(windows) to remote 

Windows directory
What FOLDER you want to move  
- ex: C:\wushka
- Says you have a folder called 200004 under it


## move to working folder
Use Cmder  
`cd C:\wushka`

## use scp to move  
Use Cmder  
`scp -ri \Users\cli\Downloads\wushka\Wushka_Dev.pem 200004\ ubuntu@ec2-13-211-158-9.ap-southeast-2.compute.amazonaws.com:`


## rename 200004\ to 200004  
Use PuTTy  
`sudo mv 200004\\/ 200004`

> You had moved the directory to {remote}/home/{login username}/200004

## To move from 'home/{login username}' to other folder
Use PuTTy  
`sudo cp -r 200003/ /var/www/html/Resources/`


