#Git 基本操作

## 1.安裝GIT

在 terminal上輸入

``` shell
sudo apt-get install git
```

安裝完成後輸入使用者名稱與email，使GIT認得這台電腦的使用者

``` shell
git config --global user.name "Your name"
git config --global user.email "123456@gmail.com.tw"
```

## 2.創建版本庫(Repository)

移動到想要創建資料庫的路徑下，輸入以下指令。

``` shell
git init
```

## 3. 基本GIT操作指令

告訴GIT將 example.txt 這個檔案加入到repository

``` shell
git add example.txt
```

告訴GIT將 example.txt 這個檔案從當前的repository 移除

``` shell
git rm example.txt
```

根GIT **確認** 到目前為止所有我們做的修改(增加檔案或者移除檔案)，並且加入對這些修改的註解

``` shell
git commit -m "這裡輸入註解"
```

掌握當前所在的repository的狀態，是否有已經變更的檔案尚未commit

``` shell
git status
```

# 4. GIT版本回朔

顯示由最新到最舊的 commit  紀錄，已確定我們要回朔到之前的哪一個版本，按q離開git log

``` shell
git log
```

將指標指向上一個commit版本

``` shell
git reset --hard HEAD^
```

指向上兩個版本

``` shell
git reset --hard HEAD^^
```

將指標指向指定的版本號，這裡用123456當例子

``` shell
git reset --hard 123456
```

搜尋git commit 的歷史紀錄，用來尋找版本號

``` shell
git reflog
```

## 5. 配合GITHUB帳號使用GIT

GITHUB 是一個社群軟體，使用者可以在上面分享自己所寫的code，也就是將自己寫的code放在GITHUB的伺服器上，此時就可以利用一些指令將帳號上面的repository clone 下來，做一些修改之後再上傳回去GITHUB的伺服器上。

將GITHUB 上 有興趣的 repository clone(下載)下來

``` shell
git clone https://github.com/您的帳號/您的repository名
```

如果有興趣的repository 是他人的repository，則必須先去該repository按下 **fork**，接著才能將該repository clone 下來。

連結遠端 github 的 repository

``` shell
git remote add origin https://github.com/您的帳號/您的repository名
```

接著可以對該repository 中的檔案做修改，修改完畢記得要用`git add` 或 `git rm`指令新增檔案或者是移除檔案，接著再使用`git commit`指令將目前所作的修改做**確認**。

最後，在該repository的路徑下，輸入以下指令將這些修改上傳到GITHUB的伺服器上

``` shell
git push -u origin master
```

接著輸入自己的GITHUB 帳號密碼，就上傳完成了。



