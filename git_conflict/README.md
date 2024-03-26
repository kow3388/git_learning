# Git conflict
在前面我們有提到過，在使用no-ff的merge時有可能會遇到conflict的情況，因此這邊要來說明如何解決conflict

## git merge tool setting
在介紹如何解決conflict之前，先來介紹如何，先來介紹如何改變git的merge tool

這邊一樣以vim為例
```
git config --global merge.tool vimdiff
git config --global mergetool.prompt false
git config --global mergetool.vimdiff.trustExitCode true
git config --global mergetool.keepBackup false
```
1. prompt的意思是啟動外部程式時是否詢問 
2. trustExitCode是設定外部程式結束後，git是否直接用他的回傳值來判斷合併是否成功
3. keepBackup是否要備份含有衝突標示的檔案

## Solve conflict
