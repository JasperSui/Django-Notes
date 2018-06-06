# Django中以靜態方式導入 css, js 檔

### 我的開發環境
> - Windows 10 
> - Python 3.6.5
> - Django 1.11


------------

### ※前置動作

需在你的 `app` 目錄下自行新增 `templates` 和 `static` 資料夾

`templates`：Django 預設 html 檔存放位置

`static`：用來存放 `css`、`js`、`fonts`、`images` 的起始資料夾，務必新增


### Step 1
　
進入 `Scripts` 中的專案資料夾 `mysite`，目錄層級如下：
　
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
|　　　　　　　　├── css/
|　　　　　　　　├── fonts/
|　　　　　　　　├── images/
|　　　　　　　　└── js/
└── manage.py
```
　
------------


### Step 2

在 `mysite/settings.py` 裡修改以下內容：


```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',

	// 原 DIRS
        'DIRS': [],

	// 修改後的 DIRS
	'DIRS': [os.path.join(BASE_DIR, 'templates'),
         os.path.join(BASE_DIR, 'static').replace('\\', '/')],
    },
]
```
　
 
 

------------


### Step 3

在 `mysite/settings.py` 最底部加入以下內容：

```
STATIC_URL = '/static/'
```
```
STATIC_ROOT = os.path.join(BASE_DIR, 'static').replace('\\', '/')
```
```
STATICFILES_DIRS = (
    ('css', os.path.join(STATIC_ROOT, 'css').replace('\\', '/')),
    ('images', os.path.join(STATIC_ROOT, 'images').replace('\\', '/')),
    ('fonts', os.path.join(STATIC_ROOT, 'fonts').replace('\\', '/')),
    ('js', os.path.join(STATIC_ROOT, 'js').replace('\\', '/')),
)
```
　
 

------------


### Step 4

在 `mysite/urls.py` 最頂部加入：

```from django.contrib.staticfiles.urls import staticfiles_urlpatterns```

及最底部加入：

```urlpatterns += staticfiles_urlpatterns()```

　
 

------------


### Step 5

在路徑前加入`/static/`

**導入 `CSS` 語法：**

```<link rel="stylesheet" href="/static/css/style.css" />```

　

**導入 `JavaScript` 語法:**

```<script src="/static/js/jquery.min.js"></script>```

　

**導入 `image` 語法：**

```<img src="/static/images/4.jpg">```

　
 

------------



### ※ 注意事項


### 1. 因為是以靜態方式取得檔案，故若有更動以上檔案，必須重啟伺服器。

### 2. 最好以無痕式視窗重新讀取頁面，以免瀏覽器根據 Cache 讀取到舊的檔案。