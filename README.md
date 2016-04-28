# learn-es6-notes
學習ES6 筆記

## let
## const
## 函數的擴展
 - 允許函數的參數給予預設值
``` js
function Point(x = 0, y = 0) {
  this.x = x;
  this.y = y;
}

var p = new Point();
p // { x: 0, y: 0 }
```


- ES6引入rest参数（形式為"...變數名稱"）
    * 這樣就不需要使用arguments了
    * rest参数搭配的變數是一個陣列
``` js
function add(...values) {
  let sum = 0;
  for (var val of values) {
    sum += val;
  }
  return sum;
}

add(2, 5, 3) // 10
```

## for-of
強大的for-of 迴圈
- 最簡潔最直接尋訪陣列元素的方法
- 避開了 for-in 循環的所有缺陷
- 與forEach() 不同的是可以正確使用 break, continue, return 等語句
``` js
for (var value of myArray) { 
  console.log(value); 
}
```
## 箭頭函數
簡化了撰寫函數內 fuction 與 return
``` js
//ES5
var foo = function(x) {
    return x + 1;
}
//ES6
const  foo = (x) => x + 1; 
```
## 反撇号 `
字串的組合,可以不用在寫 + 號
``` js
let name = 'Justin';
console.log(`my name is: ${name}`); 
//my name is: Justin
```
## Class
## Set & Map

#資源
- [ECMAScript 6入门](http://es6.ruanyifeng.com/)
- [ES6学习笔记](http://www.jianshu.com/p/7cd1e5940268)
