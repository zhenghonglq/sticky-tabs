
### 微信小程序不使用scroll-view做的吸顶+锚点


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
  <sticky scrollTop="{{scrollTop}}" navList="{{navList}}">
      <sticky-item>
      </sticky-item>
  </sticky>
```


### 主要属性

tabList为吸顶tabs中对应的数据
```json
    tabs: [{
      title: '锚点1'
    }, {
      title: '锚点2'
    }],
```


scrollTop为页面滚动的距离，使用示例如下

```js
  onPageScroll(e) {
    let scrollTop = e.scrollTop;
    this.setData({
      scrollTop
    })
  },
```

![效果图](http://files.git.oschina.net/group1/M00/07/8B/PaAvDFzJq9yAF_KQAEiKrll48dQ377.gif?token=593789cab1ef9a140c2f9d716178abec&ts=1556720604&attname=QQ20190501-214817.gif&disposition=inline)