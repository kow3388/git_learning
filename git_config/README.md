# Git config

## Git config priority
Git有三個不同priority的config檔，以下priority由高到低介紹

1. 在 ".git" 資料夾中的config:

   priority最高

2. 登入帳號的home directory裡頭的 ".gitconfig" 檔:

   當.git中的config檔未設定時，會自動去獲取此config檔

3. Git程式安裝資料夾裡頭會有一個 "/etc/gitconfig" 檔:
   
   只有當前兩者不存在時，才會去找此檔案獲取config

## Git config 指令
### 顯示Git config
以下指令會顯示上述三個設定檔(如果有設定的話，只會顯示有設定的)
```
git config -l
```

也可單獨顯示
```
顯示etc/gitconfig如果有設定的話
git config --system -l

顯示.gitconfig如果有設定的話
git config --global -l
```

### 設定Git config使用者
我們可以透過以下指令，將設定檔設定完成

1. 在 ".git" 中設定，即在此working space下的提交者
   ```
   git config user.name "使用者名稱"
   git config user.email "使用者信箱"
   ```
2. 在登入帳號的home directory裡的 ".gitconfig" 中設定
   ```
   git config --global user.name "使用者名稱"
   git config --global user.email "使用者信箱"
   ```
3. 在整個安裝系統中設定
   ```
   git config --system user.name "使用者名稱"
   git config --system user.email "使用者信箱"
   ```

通常我們會用global將登入帳號的config設定完成，因為若在每個working space設定太麻煩，而整個系統下不一定只有一個user

當發現設定錯誤時，也可以透過以下指令移除設定(以user name為例)
```
git config --unset user.name
```
也可以是情況在中間加入 "--global" 或是 "--system" ，例如
```
git config --unset --global user.name
```

### 設定Git指令別名
有時指令太長，要輸入這些指令很麻煩，可以透過設定指令別名來所短指令長度

設定別名指令
```
git config alias.指令別名 '正式的指令'
```
這邊將 "config -l" 指令設定別名為例
```
git config alias.con 'config -l'
```
此時就可以直接使用以下指令來列出config設定
```
git con
```

也一樣可以透過 "--unset" 將其別名移除
```
git config --unset alias.con
```
