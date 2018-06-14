# Django 使用 MySQL 舊有資料庫

### 我的開發環境
> - Windows 10 
> - Python 3.6.5
> - Django 1.11
> - MySQL Server 8.0

※ 如果還沒有設置資料庫，請先服用：
<a href="https://tinyurl.com/y7to5xwz"></a>

------------

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
|　　　　├── static/
|　　　　├── __init__.py
|　　　　├── admin.py
|　　　　├── apps.py
|　　　　├── models.py
|　　　　├── tests.py
|　　　　└── views.py
└── manage.py
```

### Step 1
將舊有資料庫導入 `models.py` 內

用終端機進入到專案的第一個 `mysite` 資料夾（記得啟用虛擬環境）：

> \> python manage.py inspectdb > app/models.py

### Step 2
解決 Django 在處理 MySQL 中 BIT 類型當做 TextField 處理的問題

在 `models.py` 的頂部加入：

```from django_mysql.models import Bit1BooleanField```

將

```models.TextField(blank=True, null=True)  # This field type is a guess.```

或

```models.TextField()  # This field type is a guess.```

全部取代為 ```Bit1BooleanField(default=False)```
