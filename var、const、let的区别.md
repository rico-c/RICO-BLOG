## var、const、let的区别

### var 

* 使用var关键字声明或初始化的变量，会形成变量提升

### let

* 不会变量提升。

* 在es6以前function会形成一个作用域，es6以后let定义的变量，只能在块作用域里访问 。

* 可以用let解决循环点击问题使点击对应的p元素使alert对应的p元素。

  ```
  var arr = document.getElementsByTagName("p");
      for(var i = 0;i<arr.length;i++){
          let j = i;//创建一个块级变量
          arr[i].onclick = function () {
              alert(j);
          }
      }
  ```

### const

* 声明变量时必须赋值
* 声明变量后不可更改
* 如果变量值为复杂类型或引用类型，可以改变对象的属性值。

## 解构赋值

### 数组解构赋值

* let [a,b,c] = [1,2,3];
* let [a,[b],c] = [1,[2],3];

### 数组的默认值

* 优先使用对应值，如果没有对应值则使用默认值
* undefined会使其使用默认值，null会将默认值也清空

### 对象的解构赋值

* let {a,b} = {a:1,b:2};
* 优先使用对应值，如果没有对应值则使用默认值

### 函数解构赋值

```
function sum（{x,y}={x:0,y:0},(a=1,b=1)）{
    return [x+a,y+b]
}
sum({x:1,y:2},{a:2})//[3,3]
```

## 字符串、函数、数组、对象的新写法

### 字符串

* ``用来写多行字符串
* ${}用来直接连接变量

### 数组

* ...array 可以用来将数组格式转为参数格式，如果是类数组对象可以转为数组用于遍历等方法。

### 函数

* 调用函数时如果参数为对象，默认使用传进来的参数对象，如果没有参数对象则使用默认对象

### 箭头函数

* a => a+1  等于`function(a){return a+1}` 如果没有参数则箭头左侧需要写()
*  箭头函数的this等于创建时的this

## 模块化新写法

* 新写法`export {A} ;`  `import{} from './a'`
* `export default {}` 可以使其在import时重新命名

## 类和继承

* ```
  class Person{
      constructor(name,age){
          this.name='a';
          this.age=12；
      }
      sayHello(){
          alert('how are you')
      }
  }
  ```

* static 给函数添加静态方法

* class Student extends Person{}可以继承Person。
