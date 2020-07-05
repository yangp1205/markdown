# _scrapy爬虫_

## 安装virtualenv和基础运行

- 安装virtualenv和virtualenvwrapper

```bash
pip3 install virtualenv virtualenvwrapper
```

- 配置虚拟环境

```bash
mkvirtualenv env_scrapy
```

- 安装scrapy

```bash
pip install scrapy
```

- 创建scrapy项目

```bash
mkdir scrapy_init
scrapy startproject scrapy_test
cd scrapy_test
scrapy genspider example example.com
# RUN
scrap crawl example
```

## scrapy入门

- 目录-Tree大致情况

```bash
.
├── scrapy.cfg
└── testpy
    ├── __init__.py
    ├── __pycache__
    │   ├── __init__.cpython-37.pyc
    │   └── settings.cpython-37.pyc
    ├── items.py
    ├── middlewares.py
    ├── pipelines.py
    ├── settings.py
    └── spiders
        ├── __init__.py
        ├── __pycache__
        │   ├── __init__.cpython-37.pyc
        │   └── baidu.cpython-37.pyc
        └── baidu.py

4 directories, 12 files
```

## Scrapy Settings

1. 主要框架结构
    1. scrapy爬虫的组成
        1. 引擎
        2. 爬虫中间件
        3. 调度器
        4. 下载器
        5. 下载中间件
        6. items
    2. 使用多任务处理爬虫框架
    3. yeild传输数据
2. 参数设置
3. 日志结构
4. 逻辑结构
5. 数据库
