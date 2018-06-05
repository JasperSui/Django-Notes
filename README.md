# Django 環境建置教學

### 1. 下載對應系統版本的Python 3
<a href="https://www.python.org/downloads/release/python-365/"><img src="https://i.imgur.com/PbTLOI1.png"></a>
- Win 32bits : Windows x86 executable installer
- Win 64bits : Windows x86-64 executable installer
- Mac OSx : macOS 64-bit/32-bit installer
#### ※ 安裝時請務必在 `Advanced Options` 內勾選 `Add Python to environment variables`
#### ※ 在環境變數中自動加入 Python ，在終端機就可以直接使用 python 指令。

### 2. 創建虛擬環境

#### 　開啟系統終端機
- Windows : Win+R > CMD > 執行
- Mac OSx : Terminal

#### 　輸入指令

　　**Step 1** 
  
　　安裝虛擬環境套件：
>  pip3 install virtualenv

###### 　

　　**Step 2**
  
　　以D槽為例，創建並進入 `Django` 的資料夾，之後創建並進入 `0604` 的資料夾：

　　**（ 以當下日期為例，讀者可自行更改資料夾名稱 ）**
  


> \> D:

> \> mkdir Django

> \> cd Django

> \> mkdir 0604 // 以日期為例，可自行更改

> \> cd 0604

###### 　

　　**Step 3**


　　創建虛擬環境 `jmt`，並進入 `jmt` 下的 `Scripts` 資料夾
  
　　**（ 以 jmt 為例，可自行更改虛擬環境名稱 ）**
> \> virtualenv jmt

> \> cd jmt\Scripts

###### 　

　　**Step 4**

　　啟用虛擬環境：
> \> activate.bat



　　啟用成功後會看到你的路徑變成了：
> ( jmt ) D:\Django\0604\jmt\Scripts>

###### 　

　　**Step 5**
  
　　繼續安裝 Django 套件：
> \> pip3 install django==1.11


  
　　這裡我用的是 1.11 版，讀者可以依照自己的需求來決定版本號
  
　　或是使用最新的版本號，指令如下
> \> pip3 install django

###### 　
 　　**Step 6**
   
   　　接著新增一個專案，以 `mysite` 為例，並進入 `mysite` 資料夾
   
> \> django-admin.py startproject mysite

> \> cd mysite

###### 　
 　　**Step 7**
   
   　　在 `mysite` 資料夾中，執行 `manage.py` 的 `runserver` 指令

> \> python manage.py runserver

　　　　
   　　若出現以下成功訊息，代表成功了！
   <img src="https://i.imgur.com/M3h0ad6.jpg">


### 大功告成，去 [http://127.0.0.1:8000](http://127.0.0.1:8000)

<img src="https://i.imgur.com/BC5OdPg.jpg">
