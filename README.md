# learn-es6-notes
學習ES6 筆記

## let
 - ES6新增了let，用來宣告變數
 - 它的用法類似於var, 但所宣告的變數，只在let所在的區域變數內有效。
``` js
{
  let a = 10;
  var b = 1;
}
a // ReferenceError: a is not defined.
b // 1
```
 - for loop 的計數器，就很適合使用let。
``` js
for(let i = 0; i < arr.length; i++){}
console.log(i)
//ReferenceError: i is not defined
``` 
## const
- const也用來宣告變數，但是宣告的是常數。一旦宣告，常數的值就不能改變。
``` js
'use strict';
const PI = 3.1415;
PI // 3.1415
PI = 3;
// TypeError: "PI" is read-only
```
- const的作用域與let相同：只在宣告所在的區域内有效。 
``` js
if (true) {
  const MAX = 5;
}
MAX // Uncaught ReferenceError: MAX is not defined
```
 - const宣告的常數，也與let一樣不可重複宣告。 
 
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
ES6的類別，完全可以看作建構函数的另一種寫法。

``` js
class Point{ /*...*/ }
typeof Point // "function"
Point === Point.prototype.constructor // true
```
 - 在class中 ; 符號是可選的。
 - constructor也是可選 的，如果不指定，會預設建構一個 空的constructor(){}
 - 不可以用產生器（generator）来做建構函数
 
 
 ``` js
 class Circle{
    constructor(radius){
      this.radius = radius;
      Circle.circlesMade++;
    }

    draw(circle,canvas){
      console.log('draw something')
    }

    static get circleMade(){
      return !this._count ? 0 : this.count;
    }

    static set circleMade(val){
      return this._count  = val;
    }

    area(){
      console.log(Math.pow(this.radius,2) * Math.PI)
      return Math.pow(this.radius,2) * Math.PI;
    }

    get radius(){
      return this._radius;
    }

    set radius(radius){
      return this._radius = radius;
    }

  }

  var  circle = new  Circle(3);

  circle.draw() // draw something
  circle.area() // 28.274333882308138
  circle.radius = 99;
  circle.area() // 30790.74959783356
```

- prototype對象的constructor属性，直接指向“類別”的本身，這與ES5的行為一致。


#資源
- [ECMAScript 6入门](http://es6.ruanyifeng.com/)
- [ES6学习笔记](http://www.jianshu.com/p/7cd1e5940268)
