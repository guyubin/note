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

css 的内容 三种形式

# <style>
            h1 {</p>
<pre><code>        }
    &lt;/style&gt;
    &lt;link &gt;    外部文件

元素标签加 id 或 class 进行区分
    id-h1-logo  id的格式
    gua-title   class的格式

页面布局
    1\. 盒模型  margin / padding / border / content
    2\. inline / block / inline-block
    3\. flex
    4\. float

    利用flex形成的简单三栏布局
    &lt;!DOCTYPE html&gt;
    &lt;html&gt;
        &lt;head&gt;
            &lt;meta charset=&quot;utf-8&quot;&gt;
            &lt;title&gt;三栏布局&lt;/title&gt;
        &lt;/head&gt;
        &lt;style media=&quot;screen&quot;&gt;
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
        &lt;/style&gt;
        &lt;body&gt;
            &lt;div class=&quot;header&quot;&gt;
                导航栏
            &lt;/div&gt;
            &lt;div class=&quot;container&quot;&gt;
                &lt;div class=&quot;leftsidebar&quot;&gt;
                    左栏
                &lt;/div&gt;
                &lt;div class=&quot;content&quot;&gt;
                    内容
                &lt;/div&gt;
                &lt;div class=&quot;rightsidebar&quot;&gt;
                    右栏
                &lt;/div&gt;
            &lt;/div&gt;
            &lt;div class=&quot;footer&quot;&gt;
                低栏
            &lt;/div&gt;
        &lt;/body&gt;
    &lt;/html&gt;
</code></pre></style>
