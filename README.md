# let | const
1. 生成作用域：当前代码块{}
  `function f2(){
    let n = 5;
    if(true){
        let n = 10
    }
    console.log(n)
  }`
2. 不存在变量提升，暂时性死区
3. 不允许重复声明

