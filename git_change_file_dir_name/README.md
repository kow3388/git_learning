# Git change file or directory name
在進行開發時，很常會需要修改檔案或資料夾的名稱，雖然我們可以透過 "git add ." 來達到這項目地，步驟如下
1. Chage file or directory name
2. git add .
3. git commit

git會自動去判斷說新的這個檔案和被刪掉的檔案其實是同一個檔案，因此它會以變更名稱的方式儲存，而不是儲存兩個檔案在commit中

但其實git有提供一個指令來改變檔案和資料夾名稱

## git mv
指令如下
```
git mv 舊檔案名 新檔案名
```
下了此指令後git會自動紀錄在index中，之後在commit即可

但老實說這個指令很少用到，通常會改變檔案或資料夾名稱，也會更改一些檔案內容，因此會一併用"git add ." 更新index
