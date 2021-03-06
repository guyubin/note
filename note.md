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

    html5
        语义化
            nav header ...
            自定义的标签
                <gua></gua>
            <video>
            <audio>
            配套的 js API
                video 全屏 API
                    requstFullScreen()

        localStroage sessionStorage
            前者永久保存
            后者关闭页面时消失

        html5 中属性没有空格时可以不添加引号
            属性为 boolean 值时 写了就是 true 无论给属性赋上什么值
            消除属性效果只能删除属性，使用 removeAttribute('checked')

        canvas 标签
            画布 做游戏 相关的库 particle.js phaser.js

        移动端网页
            设置 <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0 user-scalable=no">



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

    选择器
        一些不常用的选择器可以查阅阮一峰的博客

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

    媒体查询
        用来做响应式页面设计
        @media all and (min-width: 200px) and (max-width: 300px) {
            body {
                background: red;
            }
        }

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

    BOM
        BOM 是什么
            是获取浏览器信息和操控浏览器的 API

        location
            管理 URL
            location.href 可以设置当前页面
            location.reload 刷新
            http://music.163.com/#/my/m/music/playlist?id=37230882
            hash : "#/my/m/music/playlist?id=37230882"
            host : "music.163.com" （域名 + 端口）
            hostname : "music.163.com" （域名）
            pathname : "/"
            search : ""
            href : "http://music.163.com/#/my/m/music/playlist?id=37230882"

        navigator
            navigator.userAgent 得到浏览器信息
            navigator.platform

        history
            处理历史记录
            html5 中的新增 API 使得其可以作为单页面应用的实现手段的一部分

            history.length URL的数量
            history.back()
            history.forward()
            history.go(-2)

            history.pushState(null, 'title', '/profile')
                自定义对象，新页面标题，新页面的地址

                var state = {
                    page: "settings"
                }
                history.pushState(state, "settings", "/settings")

                用户点击前进，后退时，会触发window 的 popstate 事件

                window.addEventListener('popstate', function(event) {
                    var state = event.state
                    console.log('pop state', state)    
                })

                只能在相同的域下使用

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
                与 $(function()) 等价

        RequireJS
            RequireJS 主要是为了模块加载设计的小巧的框架
                1.防止js加载阻塞页面渲染
                2.程序调用方式加载，避免一堆的<script>挤在一起
            使用
                引入 require.js
                再写入 require(['a'])
            API
                define      定义一个模块
                require     加载模块，执行加载完成后的调用函数

                    require(['a'], function() {
                        alert('it works')
                    })

                requirejs   === require

                将所有的依赖模块统一写在main.js中，较为优雅直观
                因此require 有了主数据的功能
                <script data-main="js/main" src="js/require.js"></script>
                这个属性指定的 js 文件，将在 require.js 加载完后处理

                第三方模块的加载
                    符合AMD的直接加载即可，
                    如果不符合的，要用到 shim


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

后端

    Node.js
        剥除了浏览器渲染的JavaScript引擎
    Express
        后端框架，编写后端程序，在Node上运行
        例子就是文件 express_demo.js
        可以监听端口，返回响应等等
        express bodyparser 有许多的坑要注意，
            app.use(bodyParser.json())

        express 的后端代码
        ```
        var fs = require('fs')
        var express = require('express')
        var bodyParser = require('body-parser')
        var app = express()
        // 引入 express 并且创建一个 express 实例，赋值给 app
        app.use(bodyParser.json())



        var sendHtml = function(path, response) {
            var options = {
                encoding : 'utf-8'
            }
            fs.readFile(path, options, function(err, data) {
                response.send(data);
            })
        }
        // 用 get 定义一个给用户访问的网址
        app.get('/', function(req, res) {
            var path = 'index.html'
            sendHtml(path, res)
        })// req 是浏览器发送的请求，
        // res 是服务器发给浏览器的响应
        // 用 get 定义一个给用户访问的网址

        var todos =
        [
            {
                id : 1,
                task : "eat"
            }
        ]

        var addTodo = function(todo) {
            var todosLength = todos.length
            if (todosLength === 0) {
                todo.id = 1
            } else {
                todo.id = todos[todosLength - 1].id + 1
            }

            todos.push(todo)
            // var
        }

        var deleteTodo = function(id) {
            var index = -1
            for (var i = 0; i < todos.length; i++) {
                if (todos[i].id === id) {
                    index = i
                    break
                }
            }
            if (index !== -1) {
                todos.splice(index, 1)
            }
        }

        var updateTodo = function(t) {
            var id = t.id
            var index = -1
            for (var i = 0; i < todos.length; i++) {
                if (todos[i].id === id) {
                    index = i
                    break
                }
            }
            if (index !== -1) {
                todos[index].task = t.task
            }
        }

        app.get('/todo/all', function(request, response) {
            var r = JSON.stringify(todos)
            response.send(r)
        })

        // addTodo
        app.post('/todo/add', function(request, response) {
            var t = request.body
            addTodo(t)
            response.send(JSON.stringify(todos))
        })

        //delete
        app.post('/todo/delete', function(request, response) {
            var t = request.body
            var id = t.id
            deleteTodo(Number(id))
            response.send(JSON.stringify(todos))
        })

        // updateTodo
        app.post('/todo/update', function(request, response) {
            var t = request.body
            updateTodo(t)
            response.send(JSON.stringify(todos))
        })

        // listen 函数的第一个参数是我们要监听的端口
        // 这个端口是浏览器输入的
        // 默认端口是80, 所以监听的是80端口， 浏览器就不用输入
        var server = app.listen(8081, function () {

          var host = server.address().address
          var port = server.address().port

          console.log("应用实例，访问地址为 http://%s:%s", host, port)

        })

        ```
        对应的 todo 的前段代码
        ```
        <script src="//cdn.bootcss.com/jquery/3.1.1/jquery.js"></script>
        <script>
            var ajax = function() {
                $.ajax({
                    type : 'get',
                    url : '/todo/all',
                    success : function(r) {
                        console.log(r)
                    }
                })
            }

            var ajaxAdd = function(data) {
                $.ajax({
                    type : 'post',
                    url : '/todo/add',
                    data : data,
                    contentType : 'application/json',
                    success : function(r) {
                        console.log(r)
                    }
                })
            }

            var ajaxDelete = function(id) {
                $.ajax({
                    type : 'post',
                    url : '/todo/delete',
                    data : id,
                    contentType : 'application/json',
                    success : function(r) {
                        console.log(r)
                    }
                })
            }

            var ajaxUpdate = function(data) {
                $.ajax({
                    type : 'post',
                    url : '/todo/update',
                    data : data,
                    contentType : 'application/json',
                    success : function(r) {
                        console.log(r)
                    }
                })
            }
        </script>
        <body>
            <h1>hello gua</h1>
            <h2>nihao xxxx</h2>
        </body>

        ```
    Electron
        用JavaScript写本地应用的框架程序

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
        双向绑定
            对象属性发生变化时，能够改变对应的UI，反过来也是

    域名问题
        如果需要买域名可以去qcloud上买个.cc的域名
