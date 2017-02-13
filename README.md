# es6-note
## 块级绑定
`let` `const`
###知识点：
1. 块级作用域 
    ```javascript
    if(true){
        let test='test';   
    }
    console.log(test) // Error test is not defined
    ```
2. 不会有变量提升
3. 同作用域中相同变量名不可重复声明
4. `for`循环中区块变量自动生成 （用`const`声明变量会报错）
    ```javascript
    for(let i=0; i<10; i++){
        setTimeout(function(){
            console.log(i)
        },1000)
    }
    // 0 1 2 3 4 5 ...9
    
    //这并不是let本身的机制，而是语法规定中for循环中let声明每次循环都会创建一个
    //变量副本提供给函数
    
    ```
5. `for-in` `for-of` 支持`let` `const`
###总结：
*声明变量劲量用 `const`, 明确需要修改的用 `let`*