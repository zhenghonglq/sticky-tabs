
### 微信小程序吸顶+锚点组件

### 体验

<p align="center">
  <img width="200" src="http://files.git.oschina.net/group1/M00/07/8D/PaAvDFzK_4yAQcyPAADABn6A2Wc070.jpg?token=ae2d8517260e4a8e5fa9689f16825af4&ts=1556807706&attname=qr_code.jpg&disposition=inline">
</p>

### 效果图

![效果图](http://files.git.oschina.net/group1/M00/07/8D/PaAvDFzK_tiAUvfvAEmLXbHLtz4072.gif?token=3eb0a737a348d8218cd8d2a59d7e8e34&ts=1556807384&attname=show_pic.gif&disposition=inline)


### 引入组件

将 `components` 文件夹拷贝至自己的组件目录，页面 `json` 文件中配置组件

```json
{
  "usingComponents": {
    "sticky": "/components/sticky/index",
    "sticky-item": "/components/sticky-item/index"
  }
}
```

在页面 `wxml` 中引入组件
```xml
  <sticky scrollTop="{{scrollTop}}" tabList="{{tabList}}">
      <sticky-item>
      </sticky-item>
  </sticky>
```


### 主要属性

1.tabList为吸顶tabs中对应的数据
```json
    tabs: [{
      title: '锚点1'
    }, {
      title: '锚点2'
    }],
```


2.scrollTop为页面滚动的距离，使用示例如下

```js
  onPageScroll(e) {
    let scrollTop = e.scrollTop;
    this.setData({
      scrollTop
    })
  },
```


3.sync 开启响应异步容器变化高度变化的开关。

<font color=orange>注意：sync和init必须配合使用，否则无效。</font>
使用场景如下：
1） 在sticky-item中数据为异步请求
2） sticky-item中内容的需要实现显示/隐藏功能


4.init 当需要重新计算sticky-item内容器高度时，改变init的值为!init，使用示例如下

```xml
  <l-sticky sync init="{{updateSticky}}" scrollTop="{{scrollTop}}" tabList="{{tabGroups}}">
  </sticky>
```

```js
  initSticky() {
    this.setData({
      updateSticky: !this.data.updateSticky
    })
  }
```


### 下一版本为tabs增加滑动功能




