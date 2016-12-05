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
        absolute    // 会寻找父元素中最近的一个非 static 元素进行定位
        fixed

    display 属性
        block 独占一行
        inline 可以和别的一行
        inline-block 可以在一行，并可以设置宽度，高度等

    伪类
        a:hover

    调试
        可以添加以下语句使得调试更加直观
            div {outline: 1px solid red;}

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
        一些调试技巧
            所谓的“穿衣服”
            使用模板字符串给需要 log 的变量加个套
            console.log(`(${x})`)

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
        将一个数组整体一次性 push 进另一个数组中
            a.concat(arr)
            b.push.apply(b, a)

    字符串
        判断相等或者包含 '==='
        a.includes('b')

        ES6 中的模板字符串
            var name = 'gua'
            var a = `${name}, 你好`

        字符串也可以用下标形式进行访问 s[0]

        字符串切片 s.slice(0, 3)

    编码
        encodeURIComponent() // 编码
        decodeURIComponent() // 解码

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

    面向对象
        var Student = function(name, height) {
            this.name = name
            this.height = height
        }
        var s1 = new Student()

        Student.prototype.... = 原型方法

    关于动态绑定 this 的一点东西
        this 执行动态绑定，但是可以使用 bind apply call 绑定到指定的对象上
            bind：
                var o = {
                    foo : 1,
                    bar : function() {
                        return this.foo
                    },
                }
                o.bar() // 1
                var b = o.bar.bind(o)
                b() // 1
            apply:
                log 函数
            call
                和 apply 近似，就是 apply 具有解包的能力，而 call 不具备

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

        事件捕获和冒泡
            冒泡为默认的方法 从底层到上层
            addEventListener 的第三个参数为 true 代表 useCapture 为true
            同一个目标上 先 冒泡 再 捕获

        Ajax
            var r = new XMLHttpRequest()
            r.open('GET', '/login', true) 第三个参数表明是否异步 ， true为异步
            r.setRequestHeader('Content-Type', 'application/json')
            r.onreadystatechange = function() {
                console.log('state change', r)
            }

            r.send()

            r.readystate = 4 代表收到服务器响应


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

        data属性
            dom: domDiv.dataset.<id>
            jquery: jqdiv.data('id')

        ES6
            let 快作用域的 var
            const 不能修改的常量
                const = 1
                const arr = [1,2]
                arr.push(3)
            set 集合 类似数组 无重复元素
                var s = new Set()
                s.add()
                s.size
                s.delete()
                s.has()
            Map
                var m = new Map()
                m.set('name', 'gua')
                m.get('name')
            ... 扩展符号
                var a1 = [1,2,3]
                var a2 = [...a1, 4] === [1,2,3,4]
            解包
                var [a,b] = [b,a]
            函数默认参数
                var foo = function(a, name = 'gua') {
                    log(a, name)
                }
            箭头函数
                匿名函数的简化
                this 是完全绑定了的
                没有 arguments 对象
                (参数1，参数2) => {语句}
            新增函数
                includes

        jQuery
            a. 选择器
                1. $
                2. find   例如：$("#orderedlist).find("li")
                3. siblings
                4. closest, parent
                $('body')
                $('#id-button-add')
                $('.cell')
            b. dom操作
                1. append
                2. remove
                3. empty // 与 remove 的区别在于 remove 删除整个元素，而 empty 删除选中内部的全部
                4. show hide toggle
            c. class 操作
                1. addClass removeClass
                2. toggleClass
            d. 属性、特性操作
                1. attr prop data
                2. removeAttr
            e. 取值
                1. val  // 取input 的值
                2. text // 只取文本，忽略标签
                3. html // 相当于innerHTML
            f. 事件
                1. on 相当于 addEventListener
                    $('.delete-button').on('click', function(event) {
                            var button = $(event.target)
                        button.closest('.todo-cell').remove()
                        })
                    事件委托
                    $('#id-div-todo').on('click', '.delete-button', function(){})
                        第二个参数是事件委托的对象
                    事件冒泡 阻止
                    $('span').bind("click",function(event){
                        var txt = $('#msg').html() + "<p>内层span元素被点击.<p/>";
                        $('#msg').html(txt);
                        event.stopPropagation();    //  阻止事件冒泡
                    });
                2. change
                3. event.target
            g. 数组方法
                1. each
                    (index, value)
                2. map
                    相当于以前的process
                3. grep
                    相当于以前的filter
            h. ajax
                $.ajax({
                    url: ,
                    type: 'get',
                    contentType: 'application/json',
                    success:
                    error:
                    })

            $('document').ready(function(){}) // 加载完立即执行

HTTP
        https://movie.douban.com/chart
        http and https present the protocal
        movie.douban.com 主机名
        端口：一般默认80 ，且省略
        /chart: 路径

        不同电脑主机之间的通信通过IP地址，一般为数字，但是因为数字不好记忆，因此
        发明了域名，
        域名与IP地址之间的对应关系，存储在DNS服务器之中

        可以使用 ping 命令查看

        端口是程序的对应接口

        http协议
            双方都遵循的一种规范格式
            分为4个部分
                请求行 响应行 GET /  /..
                http头
                /r/n/r/n 作为http头与http body 之间的分割
                内容



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

    object.keys(obj) 返回给定对象可枚举属性组成的数组
    window.location.href = 'http://www.wrox.com'    改变浏览器当前页面位置

    给 style 加上 class， 可以在删除元素时，一起删除与其绑定在一起的 style

    使用 github 显示 demo 页面
        创建一个仓库 guyubin.github.io
        将需要展示的页面直接放入仓库，
            例如：
                <!DOCTYPE html>
                <html>
                    <head>
                        <meta charset="utf-8">
                        <title>HelloWorld</title>
                    </head>
                    <body>
                        HelloWorld
                    </body>
                </html>
            直接新建一个文件 helloworld.html 保存上述 html 代码
        将 helloworld.html 放入仓库 guyubin.github.io 中
        在浏览器键入 guyubin.github.io/helloworld.html 即可见demo

    DOM 操作上的 trick
        input checked 复选框 被选中项的 prop 属性值为 true
        prop('checked') === true    
