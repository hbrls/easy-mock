注意！！！
==

1. 原 https://github.com/hbrls/docker-easy-mock 不再维护
2. 现项目是一个临时的 fork，部分代码待和官方沟通，部分代码还在重构过程中；目前只支持本人公司内部部署

BUILD
==

```
$ docker build -t hbrls/easy-mock:1.3.0 .
$ docker run -it --rm hbrls/easy-mock:1.3.0 bash
```

CHANGELOG
==

v1.3.0

1. node@8.6.0
2. $ npm install mv@2.1.1
