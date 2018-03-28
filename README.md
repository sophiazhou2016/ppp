# 1. let | const
1. 生成作用域：当前代码块{}
```
  function f2(){
    let n = 5;
    if(true){
      let n = 10
    }
    console.log(n)
  }
```
2. 不存在变量提升，暂时性死区
3. 不允许重复声明
    const实际上保证的，并不是变量的值不得改动，而是变量指向的那个内存地址不得改动。
    ES5 只有两种声明变量的方法：var命令和function命令。ES6 除了添加let和const命令，后面章节还会提到，另外两种声明变量的方法：import命令和class命令。所以，ES6 一共有 6 种声明变量的方法
# 2. 强制参数
  es6提供了默认参数的概念，当函数的值没有传入或者undefined的时候，会应用参数的默认值。
  ```
    const required = () => {throw new Err('Missing parameter')}
    const add = (a = required(), b = required()) => {a + b}
    add(1,2,) // 3
    add(1) // Missing parameter
  ```
# 3. reduce #
  不明白的基础用法的，参考：https://segmentfault.com/a/1190000005921341
  ## 使用 reduce 替代 map + filter ##
  ```
    const numbers = [10, 20, 30, 40];
    const doubledOver50 = numbers.reduce((finalList, num) => {
      console.log('finalList:', finalList)
      num = num * 2; //double each number (i.e. map)
    
      //filter number > 50
      if (num > 50) {
        finalList.push(num);
      }
      return finalList;
    }, []); // 回调函数的第二个参数值finalList的初始值
  ```
# 4. 对象解构 #
  ## 去除对象多余的项 ##
  ```
    let {_internal, tooBig, ...cleanObject} = {el1: '1', _internal:"secret", tooBig:{}, el2: '2', el3: '3'};
 
    console.log(cleanObject); // {el1: '1', el2: '2', el3: '3'}
  ```
  ## 合并对象 ##
  ```
  let object1 = { a:1, b:2,c:3 }
  let object2 = { b:30, c:40, d:50}
  let merged = {…object1, …object2} //spread and re-add into merged
  ```
# 5. 使用 Sets 数组去重 #
  ```
    let arr = [1, 1, 2, 2, 3, 3];
    let deduped = [...new Set(arr)] // [1, 2, 3]
  ```
# 6. 数组解构 #
  a) 交换变量的值
  ```
    let param1 = 1;
    let param2 = 2;
    //swap and assign param1 & param2 each others values
    [param1, param2] = [param2, param1];
    console.log(param1) // 2
    console.log(param2) // 1
  ```
  b) 从函数接受和分配多个值
    

参考文档： http://www.ferecord.com/check-out-these-useful-ecmascript-2015-es6-tips-and-tricks.html