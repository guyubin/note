html 的内容

```
<!DOCTYPE html> 套路

html 的注释 <!--            -->

<> 中的内容就是标签

    <html> </html>
    <body> </body>

        标签中有属性， 例如 <img src="">

        一些标签
            <div> 分割布局
            <p>   表示段落

            <strong> 加粗
            <em>     斜体
            <span>   圈出元素，但是没有特别的形式

            超链接 <a href="#"> </a>

            <input type="" value=""> type决定了input标签的形式，value是值
```

css 的内容

    三种形式

    <style>
            h1 {

            }
    </style>
    <link>    外部文件

    元素标签加 id 或 class 进行区分    

    id-h1-logo  id的格式    
    gua-title   class的格式    

    页面布局   

    1\. 盒模型  margin / padding / border / content
    2\. inline / block / inline-block
    3\. flex
    4\. float

    样式优先级
        !important
        内联
        <style>
        <link>

    选择器优先级
        !important
        内联
        id
        class
        元素

    元素定位
        static
        relative
        absolute
        fixed

    display 属性
        block 独占一行
        inline 可以和别的一行
        inline-block 可以在一行，并可以设置宽度，高度等

    伪类
        a:hover

    利用flex形成的简单三栏布局
    ```
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>三栏布局</title>
        </head>
        <style media="screen">
            div {
                outline: 1px dashed red;
            }
            .container {
        display: flex;
        width: 80%;
        margin: 0 auto;
    }
    .leftsidebar {
        flex-grow: 1;
    }
    .content {
        flex-grow: 5;
    }
    .rightsidebar {
        flex-grow: 1;
    }
        </style>
        <body>
            <div class="header">
                导航栏
            </div>
            <div class="container">
                <div class="leftsidebar">
                    左栏
                </div>
                <div class="content">
                    内容
                </div>
                <div class="rightsidebar">
                    右栏
                </div>
            </div>
            <div class="footer">
                低栏
            </div>
        </body>
    </html>
```

javascript
    调试函数
        var log = function() {
            console.log.apply(console, arguments)
        }

    if ... else ...
    逻辑操作，比较运算
        && ，|| ， ！
        ===， ！==， 等
    函数返回值
        return
    标准库
        Math 等

    array 数组
        数组中元素的值得类型可以不同
        a.length 表示数组的长度
        可以用 a[] 对数组元素进行访问
        循环访问数组的元素，即是遍历
        a.push(jkjf) 向数组末尾添加元素
        删除某个元素 array.splice(0,2) // 第一项的位置， 和要删除的项数

    字符串
        判断相等或者包含 '==='
        a.includes('b')

        ES6 中的模板字符串
            var name = 'gua'
            var a = `${name}, 你好`

        字符串也可以用下标形式进行访问 s[0]

        字符串切片 s.slice(0, 3)

    测试函数
        ensure 函数
        var ensure = function(condition, message) {
            if (!condition) {
                console.log(message)
            }
        }

        break 终止循环
        continue 跳过单次循环

    数据类型
        number
        string
        boolean
        null
        undefined

        object

        函数也是一个值

        用 typeof 判断类型

        高阶函数 函数作为参数传递
            var process = function(array, processor) {}
        函数两种形式
            函数声明
                function sum(a, b) {
                    return a + b
                }
            函数表达式
                var sum = function(a, b) {
                    return a + b
                }

    object 对象
        var taoer = {
            'name': 'gua',
            'height': 169,
        }

        访问
            taoer['name']
            taoer.name
        增加
            gua['sex'] = 'male'
        修改
            gua.name = 'gua'
        删除
            delete gua.sex

    递归

    DOM 操作
        查询  document.querySelector()
        获得属性 getAttribute()
        设置属性 setAttribute()
        是否有该属性  hasAttribute()
        删除属性    removeAttribute()
        获得所有属性 user.attributes

        操作元素
            创建  document.createElement()
            添加  appendChild()   form.insertAdjacentHTML('', '')
            删除  parentElement.removeChild()
            访问父节点 pwd.parentElement
            删除自己  pwd.remove()

        事件
            1.获得元素
            2.声明函数
            3.绑定   addEventListener()

        事件委托
            给运行时添加的元素绑定事件，

        存储
            localStroage
            localStorage.name 设置属性，即可存储数据
                              删除， localStorage.removeItem('name')
                              localStorage 的大小是 5M
        Json                  
            数组和对象用string 进行转换时存在缺陷，
            因此产生了Json 数据格式，对其进行序列化和反序列化

            var s = JSON.stringify([1,2,3,3])
            JSON.parse(s)


Some Tricks

    chrome 有焦点时的蓝色框是outline属性，是 agent user style
    在程序中添加一个函数作为程序的单一入口
        var __main = function() {

        }
        最后调用该函数

    blur事件的特殊性，不冒泡

    打表 例如
        var formatWeekDay = function(day) {
            var weekDay = {
                '1' : '星期一',
                '2' : '星期二',
            }
        }
