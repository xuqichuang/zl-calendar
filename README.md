# zl-calendar

> 臻旅日历组件

## 引入组件

```
npm install zl-calendar -S
```

## 全局引用方法
> main.js 中引入

```
import zlCalendar from 'zl-calendar'
Vue.use(zlCalendar)
```

### zlCalendar
> 仿照美团酒店编写的日历组件，展示选中区间
> [臻旅所有组件地址](https://github.com/xuqichuang/zl-vue-ui)
###### 使用方法

> html
```
<button @click="calendarShow"></button>
<zl-calendar ref="zlCalendar" @change="calendarChange"/>
```
> js

```
data:{
    selectedData:[]
}
calendarShow(){
  this.$refs.zlCalendar.show()
},
calendarChange(val){
    this.selectedData = val
}
```
> props

```
close:{ // 关闭文字
  type: String,
  default:'×'
},
color:{ //选中的背景色
  type: String,
  default:'rgb(17,55,160)'
},
lightColor:{ // 开始结束之间的背景色
  type: String,
  default: `rgb(17,55,160,.15)`
},
title:{ //标题文字
  type: String,
  default:'选择日期'
},
months:{ // 月份长度
  type: [Number,String],
  default:6
},
type:{ // 选择类型 // start 开始, end 结束, double 双选
  type: String,
  default: 'double', 
},
selectedDate:{ // 默认选中日期
  type: Array,
  default(){
    return [
      moment().format('YYYY-MM-DD'),
      moment().add(1, 'd').format('YYYY-MM-DD')
    ]
  }
},
selectedText:{ //选中的文字，顺序不可颠倒
  type:Array,
  default(){
    return ['入店','离店']
  }
}
```
> events

```
change
返回值：Array selectedDate
```