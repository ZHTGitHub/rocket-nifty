# nifty-util

nifty-util是一个实用而简单的JavaScript工具库。

## 安装

从GitHub上下载[最新的nifty-util](https://github.com/ZHTGitHub/nifty-util)，或使用[npm](https://github.com/ZHTGitHub/nifty-util)安装:

```bash
npm install nifty-util
```

## 如何使用

```bash
import util from 'nifty-util'
// or
import { isEqual } from 'nifty-util'
```

### isEqual(val1, val2)

判断两个值是否绝对相等，数组/对象只比较其属性值是否绝对相等

#### Arguments

val1: 任意值

val2: 任意值

#### Returns

(boolean): 若两个值绝对相等返回true，否则返回false.


#### Example

```bash
const result = isEqual(1, '1')
console.log(result)
// => false
```

### isYummy(value)

判断值是否合法

#### Arguments

value: 任意值

#### Returns

(boolean): 若值不为undefined、null、false、空字符串、空数组、空对象返回true，否则返回false.


#### Example

```bash
const result = isYummy({})
console.log(result)
// => false
```

### getScrollOffset()

返回滚动条滚动距离

#### Arguments

--

#### Returns

({ x: number, y: number }): x为横坐标滚动距离，y为纵坐标滚动距离.


#### Example

```bash
const result = getScrollOffset()
console.log(result)
// => { x: 0, y: 100 }
```

### getViewportSize()

返回浏览器视口尺寸

#### Arguments

--

#### Returns

({ width: number, height: number }): width为视口宽度，height为视口高度.


#### Example

```bash
const result = getViewportSize()
console.log(result)
// => { width: 1920, height: 1080 }
```

### queryToObject(search)

将 url 参数解析为 JS 对象

#### Arguments

search: url参数

#### Returns

(Object): 一个新的对象.


#### Example

```bash
const objUrl = new URL('http://github.com?name=leslie&gender=male')
const result = queryToObject(objUrl.search)
console.log(result)
// => { name: 'leslie', gender: 'male' }
```

### date(value)

返回日期的详细信息

#### Arguments

value: 字符串日期/日期对象，不传则为当前时间.

#### Returns

({ 

  year: number, 

  month: number, 

  day: number, 

  date: number, 

  hours: number, 
  
  minutes: number, 

  seconds: number, 

  milliseconds: number, 

  time: number, 

  normalMonth: number, 

  am00Time: number, 

  pm24Time: number 

}): year年, month当前月份(0-11), day周, date日, 

hours时, minutes分, seconds秒, milliseconds毫秒, 

time自 1970 年 1 月 1 日 00:00:00 UTC 到当前时间的毫秒数, 

normalMonth当前月份(1-12), 

am00Time为0点, pm24Time为24点.

|  属性   | 说明  | 类型  |
|  ----  | ----  | ----  |
| year   | 年份  | number  |
| month  | 月份  | number  |


#### Example

```bash
const result = date()
console.log(result)
// => 
{ 
  am00Time: 1677081600000, 
  date: 23, 
  day: 4, 
  hours: 10, 
  milliseconds: 680, 
  minutes: 49, 
  month: 1, 
  normalMonth: 2, 
  pm24Time: 1677167999999 
  seconds: 36, 
  time: 1677120576680, 
  year: 2023 
}
```

### set(object, path, value)

设置对象路径处的值

#### Arguments

object: 要修改的对象
path: 要设置的属性的路径
value: 要设置的值

#### Returns

(Object): 返回的对象.


#### Example

```bash
const obj = {}
const result = set(obj, 'a.b', 1)
console.log(result)
// => { a: { b: 1 } }
```

### get(object, path, defaultValue)

获取对象路径处的值

#### Arguments

object: 要查询的对象
path: 要获取的属性的路径
defaultValue: 为未定义的解析值返回的值

#### Returns

(*): 返回解析值.


#### Example

```bash
const obj = {a: {b: 1}}
const result = set(obj, 'a.b')
console.log(result)
// => 1
```


