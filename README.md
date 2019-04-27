# RPZ VIDEO
 基于“视点网” 二次开发 (Forked from v.mypython.me)

## 配置文件
  请注意根据 `RpzVideo/RpzVideo/settings.py`
  
  里面的配置属性对应本机相关内容合理更改。

## 克隆项目到本地之后
1. 在自己本地的 MySQL server 中新建数据库：
    ```mysql
    create database video;
    ```

2. 通过 manage.py 迁移数据库表模型
    若您的环境中同时存在 **python2** 和 **python3**
    
    则请使用 `python3` 而不是 `python`
    ```bash
    python manage.py migrate auth
    python manage.py makemigrations users
    python manage.py migrate users
    python manage.py migrate --fake admin
    python manage.py migrate
    python manage.py makemigrations video
    python manage.py migrate video
    python manage.py makemigrations comment
    python manage.py migrate comment
    python manage.py makemigrations myadmin
    python manage.py migrate myadmin
    ```

3. 如何运行本后端服务?
    1. 创建后台管理超级用户：
    ```bash
    python manage.py createsuperuser
    ```
    
    2. 启动服务器
    ```bash
    python manage.py runserver
    ```