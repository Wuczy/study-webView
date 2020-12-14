# CSS学习 Day1
## 1.CSS简介
网页分成三个部分，结构(HTML)、表现(CSS)、行为(JavaScript)。

CSS：
1. 层叠样式表
2. 网页实际上是一个多层结构，通过CSS可以分别为网页的每一层来设置样式，而最终用户看到的只是网页最上边的一层
3. 言而总之，CSS用来设置网页中元素的样式

## 2.CSS编写的位置
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>

    <!-- 第二种方式 -->
    <style>
        p{
            color: green;
            font-size: 50px;
        }
    </style>

    <!-- 第三种方式，如果和第二种方式设置同一个元素的样式，第三种会覆盖第二种 -->
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!--
        使用css来修改元素的样式

        第一种方式：内联方式，行内样式(不推荐使用)
            - 在标签内部通过style熟悉来设置元素的样式
            - 样式只能对一个标签生效，如果需要设置多个元素，每个元素都需要设置style属性
            - 当样式发生变化时，必须一个一个修改，不方面维护，开发时不要使用这种方式
        -->
    <p style="color: orange; font-size: 30px;">orange code</p>
    <!-- 
        第二种方式：内部样式表
            - 将样式编写到head的style标签里
            - 通过css选择器来选中元素并未其设置各种样式，可以同时为多个标签设置样式，并且修改时只需要修改一处就可以全部应用
            - 只能当前网页有效，不能跨页面进行复用
     -->
     <p>路遥知马力，日久见人心</p>
     <!-- 
         第三种方式：外部样式表（最佳实践）
            - 将css样式编写到一个外部的css文件中，在head中通过link标签引入外部的css文件
            - 只要想使用这些样式引入即可，实现了不同页面之间的复用
            - 将样式编写到外部的css文件中，可以使用到浏览器的缓存机制，从而加快网页的加载速度，提高瀛湖的体验
      -->
</body>
</html>
```

## 3.CSS的基本语法
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=, initial-scale=1.0">
    <title>Document</title>

    <style>
        /*
        css中的基本语法：
            选择器 声明块
            
            选择器：通过选择器可以选中页面中的指定元素
            声明块：通过声明块来指定要为元素设置的样式
                声明块由一个一个的声明组成，声明是一个键值对，以:连接，以;结尾。
         */
         h1{
             color: green;
             font-size: 123px;
         }
    </style>
</head>
<body>
    <h1>ssss</h1>
</body>
</html>
```

## 4.CSS常用选择器
常用选择器主要有四个：标签选择器，id选择器，类选择器，通配选择器。
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 
        1.元素选择器：根据标签名来选中指定元素
        */
        h1{
            color: indianred;
        }
        p{
            color: indigo;
        }
        /* 
        2.id选择器：根据元素的id属性值选中一个元素
        */
        #wcz{
            color: orange;
        }
        /* 
        3.类选择器：根据元素的class属性值选中一组元素
        */
        .czy{
            color: orangered;
        }
        .dd{
            font-size: 50px;
        }
        /* 
        4.通配选择器：选中页面中的所有元素（改变不了已经设置了样式的元素）
        */
        *{
            color:blue;
        }
    </style>
</head>
<body>
    <h1 class="dd">《事林广记》卷九</h1>
    <p id="wcz">流水下滩非有意，白云出岫本无心。</p>   
    <p class="czy dd">路遥知马力，事久见人心。</p>
    <p class="czy">马行无力皆因瘦，人不风流只为贫。</p> 
    
</body>
</html>
```

## 5. 复合选择器
分为交集选择器和并集选择器
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        /* 
        1.交集选择器：选中同时复合多个条件的元素。
            语法：选择器1选择器2..选择器n{}
            注意：交集选择器中如果有元素选择器，必须使用元素选择器开头
        */
        div.blue{
            color: blue;
        }
        .a.b.c{
            color: orangered;
        }
        /* 
        2.并集选择器：同时选择多个选择器对应的元素。
            语法：选择器1,选择器2，..选择器n{}
        */
        h1,span{
            color: green;
            font-size: 30px;
        }
    </style>
</head>
<body>
    <div class="blue">我是div</div>
    <p class="a b c">ppppp</p>

    <h1>标题</h1>
    <span>内容</span>
</body>
</html>
```