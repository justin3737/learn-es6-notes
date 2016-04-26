# learn-es6-notes
學習ES6 筆記

## 函數的擴展
允許函數的參數給予預設值
```
function Point(x = 0, y = 0) {
  this.x = x;
  this.y = y;
}

var p = new Point();
p // { x: 0, y: 0 }
```
ES6引入rest参数（形式為"...變數名稱"）
```
function add(...values) {
  let sum = 0;

  for (var val of values) {
    sum += val;
  }

  return sum;
}

add(2, 5, 3) // 10
```
## for loop
## 箭頭函數
## Iterator 疊代器
## 反撇号 `
## Class
## Set & Map
## let
## const

#資源
[ECMAScript 6入门](http://es6.ruanyifeng.com/)

[ES6学习笔记](http://www.jianshu.com/p/7cd1e5940268)
