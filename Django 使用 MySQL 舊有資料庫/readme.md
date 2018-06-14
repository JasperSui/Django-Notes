# Django �ϥ� MySQL �¦���Ʈw

### �ڪ��}�o����
> - Windows 10 
> - Python 3.6.5
> - Django 1.11
> - MySQL Server 8.0

�� �p�G�٨S���]�m��Ʈw�A�Х��A�ΡG
<a href="https://tinyurl.com/y7to5xwz"></a>

------------

�M�ץؿ��p�U�G
```
mysite/
�u�w�w mysite/
|�@�@�@�@�u�w�w __init__.py
|�@�@�@�@�u�w�w settings.py
|�@�@�@�@�u�w�w urls.py
|�@�@�@�@�|�w�w wsgi.py
�u�w�w app/
|�@�@�@�@�u�w�w migrations/
|�@�@�@�@�u�w�w templates/
|�@�@�@�@�u�w�w static/
|�@�@�@�@�u�w�w __init__.py
|�@�@�@�@�u�w�w admin.py
|�@�@�@�@�u�w�w apps.py
|�@�@�@�@�u�w�w models.py
|�@�@�@�@�u�w�w tests.py
|�@�@�@�@�|�w�w views.py
�|�w�w manage.py
```

### Step 1
�N�¦���Ʈw�ɤJ `models.py` ��

�β׺ݾ��i�J��M�ת��Ĥ@�� `mysite` ��Ƨ��]�O�o�ҥε������ҡ^�G

> \> python manage.py inspectdb > app/models.py

### Step 2
�ѨM Django �b�B�z MySQL �� BIT ������ TextField �B�z�����D

�b `models.py` �������[�J�G

```from django_mysql.models import Bit1BooleanField```

�N

```models.TextField(blank=True, null=True)  # This field type is a guess.```

��

```models.TextField()  # This field type is a guess.```

�������N�� ```Bit1BooleanField(default=False)```
