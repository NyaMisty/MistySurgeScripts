# 闲鱼搜索关键字过滤

## 原因：

一堆恶心人的暂挂、求购，占用大量屏幕

## 相关接口：

```
https://acs.m.goofish.com/gw/mtop.taobao.idle.search.glue/8.0
```

## 脚本逻辑

- 解析返回JSON，按照 ret.data.resultList[].data.item.main.exContent.title判断关键字


## 特殊情况

- 闲鱼会绕开dns直接请求https，需要添加 `force-http-engine-hosts` 来强制解析TLS
    - 首次搜索时会卡一段时间
