# 微信小程序开发框架wexp文档

## 快速入门指南

### 使用 npm 创建 wexp 项目
这里就不介绍安装和创建项目了详情可以查看[安装于创建教程](https://chaunjie.github.io/kui/dist/#/start)


### API

#### page

| 参数 | 说明 | 类型 | 使用方法 | 参数 |
|---------------------|----------------------------|-----------|-----------|-------------|
| $parent | 页面通过该参数可以直接获取到小程序全局信息 | `Object` |`this.$parent` | ` ` |
| $getCurrentPage | 页面通过该方法可以直接获取到当前页面上下文信息 | `Function` |`this.$getCurrentPage()` | ` ` |
| $query | 页面通过该方法可以直接获取到dom信息(注意返回的是一个promise对象) | `Function` |`this.$query('#id')` | `需要选择的dom的id或者class` |
| $route | 页面通过该方法进行页面之间的跳转 | `Function` |`this.$router(type, path, params)` | `type：跳转的类型（navigate、redirect、switch）三种类型，分别代表（navigateTo、redirectTo、switchTab）， path代表路径（例： '../login/index'）， params代表参数(例：{name: 'xxx', id: 'xxx'})` |
| $back | 页面通过该方法进行页面退回 | `Function` |`this.$back()` | `num代表回退几个页面，默认num为1` |

##### 页面支持使用watch和computed属性

```javascript
computed = {
  getName () {
    const {obj} = this.data
    return obj.obj.name
  }
}

 watch = {
  page (newValue) {
    console.log(newValue)
  },
  arr (newValue) {
    console.log(newValue)
  },
  obj (newValue) {
    console.log(newValue)
  }
}
```



#### component

| 参数 | 说明 | 类型 | 使用方法 | 参数 |
|---------------------|----------------------------|-----------|-----------|-------------|
| $app | 组件通过该参数可以直接获取到小程序全局信息 | `Object` |`this.$app` | ` ` |
| $getCurrentPage | 组件通过该方法可以直接获取到当前页面上下文信息 | `Function` |`this.$getCurrentPage()` | ` ` |
| $query | 页面通过该方法可以直接获取到dom信息(注意返回的是一个promise对象) | `Function` |`this.$query('#id')` | `需要选择的dom的id或者class` |
