# Git 清理repository
git repository在經過長時間的存取和更動後，git的備份資料會變得很多，但其實有些資料是不會再使用的

假設完全不去理它，其實git還是可以正常運作，只是效率會變得差一些，而且會浪費硬碟空間

這時就可以使用 "git gc" 的指令來清理repository

## git gc
"gc" 其實是garbage collection的縮寫，此指令是用來優化git的repository清除不再需要的文件等資料，指令如下
```
git gc
```
當然直接下 "git gc" 就可以了，但也可以搭配一些選項來做搭配
1. \-\-aggressive
	```
	git gc --agressive
	```
	加入此選項，git會更加仔細的進行垃圾收集及清理，但會需較久的時間，偶爾使用即可，太常用凡而沒什麼幫助

2. \-\-auto
	```
	git gc --auto
	```
	加入此選項，git會自動判斷repository是否需要清理，如果情況還良好，git就不會執行清理動作 

3. \-\-no-prune
	```
	git gc --no-prune
	```
	此選項是要求git不要清理repository那些不會用到的資料，只要 "整理" 即可

4. \-\-prune=\<date\>
	```
	git gc --prune=<date>
	```
	此選項是將特定時間點前未被使用的資料刪除，以下給兩個範例
	```
	git gc --prune=now
	git gc --prune=2023-12-01
	```

這邊要注意執行 "git gc" 可能會使得repository一段時間不可用，因為git在執行期間會鎖定repository，此外因為有執行一些刪除的動作，可能會使得一些歷史操作變得不可逆
