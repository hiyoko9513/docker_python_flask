# 新規プロジェクト作成手順

1. django の新規プロジェクト作成

```shell
make django-create
```

2. setting.py の DB の変更

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'hiyoko',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': 'db',
        'POST': 3306
    }
}
```

3. サイトの起動

```shell
make up
```
