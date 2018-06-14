# Django 設置 MySQL 資料庫

### 我的開發環境
> - Windows 10 
> - Python 3.6.5
> - Django 1.11


------------

### Django 支援的資料庫系統有
- SQLite ( 預設資料庫 )
- MySQL ( 本文範例 )
- Oracle
- PostgreSQL

#### 話不多說，直接進入正題吧！

專案目錄如下：

```
mysite/
├── mysite/
|　　　　├── __init__.py
|　　　　├── settings.py
|　　　　├── urls.py
|　　　　└── wsgi.py
├── app/
|　　　　├── migrations/
|　　　　├── templates/
|　　　　└── static/
└── manage.py
```

### Step 1
進到 `Scripts` 資料夾啟用虛擬環境 `activate.bat`之後，

安裝適用於 Python 3 的 MySQL 套件：

> \> pip install mysqlclient
> \> pip install django_mysql

### Step 2
`mysite/settings.py`

將 `DATABASES` 標籤的屬性內容修改如下即可：
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'schema',    # 資料庫名稱
        'USER': 'root',
        'PASSWORD': 'password',    # 安裝 MYSQL 資料庫時，root 用戶的密碼
        'HOST': '127.0.0.1',
    }
}
```
