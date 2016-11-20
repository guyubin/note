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
