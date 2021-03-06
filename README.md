# 超轻量级 View 库   [![npm](https://img.shields.io/npm/v/tiny-view.svg)](https://www.npmjs.com/package/tiny-view)  [![npm](https://img.shields.io/npm/dt/tiny-view.svg)](https://www.npmjs.com/package/tiny-view)

超轻量 View 库，使用方法类似 Backbone.View，依赖 jquery(1.8+)。

## Get Started

```
var Demo = View.extend({
    el: '<div class="test"></div>',
    init: function(opts) {
        console.log('init', opts.name)
        this.render()
    }, 
    events: {
        'click button': 'clickFunc'
    },
    render: function(){
        this.$el.html('<button>Click me!</button>')
    },
    clickFunc: function() {
        alert('u click me')
    }
})
var demo = new Demo({
    name: 'demo'
})
```

## 配置参数

### el { String }

View 的根 dom 对象，可以是一段html代码或者一个选择器。

### init { function }

创建View时，调用的初始化函数。

### events { Object }

配置监听的事件和回调函数。

```
events: {
    'event selector': 'function name'
}
```

## API

### el { Object }
  
View 的原生dom对象。

```
var view = View.extend({...})
view.el
```

### $el { Object }

View 的 jquery 对象。

```
var view = View.extend({...})
view.$el
```

### $ { function }

jquery 选择器

```
var view = View.extend({...})
view.$('selector')
```
### destroy { function }

销毁 View，同时解绑绑定到 View 上的事件。

### opts { any }

初始化 View 时，传递的参数
```
var DemoView = View.extend({...})
var view = new DemoView(opts) //opts === this.opts
```

### data { Object }

初始化 View 时，会自动初始化 data 属性为一个空对象，View 内的数据应该都挂载在 data 上统一管理。

### 其他没有了，就是这么简单。

