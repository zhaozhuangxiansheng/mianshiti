# HTML
### HTML语义化

```
    HTML语义化就是让页面内容结构化，它有如下优点:
        1、易于用户阅读，样式丢失的时候能让页面呈现清晰的结构。
    2、有利于SEO，搜索引擎根据标签来确定上下文和各个关键字的权重。
    3、方便其他设备解析，如盲人阅读器根据语义渲染网页
    4、有利于开发和维护，语义化更具可读性，代码更好维护，与CSS3关系更和谐
    
    例如:
        <header>代表头部
        <nav>代表超链接区域
        <main>定义文档主要内容
        <article>可以表示文章、博客等内容
        <aside>通常表示侧边栏或嵌入内容
        <footer>代表尾部
    
    HTML5新标签:
        <header>、<footer>、<aside>、<nav>、<video>、<audio>、<canvas>等...

```

# CSS
### 盒子模型
```
    盒模型分为标准盒模型和怪异盒模型(IE模型)
        box-sizing：content-box   //标准盒模型
        box-sizing：border-box    //怪异盒模型
        
    标准盒模型：
        元素的宽度等于style里的width+margin+border+padding宽度
    
    怪异盒模型：
        元素宽度等于style里的width宽度
    
    注意：
        如果你在设计页面中，发现内容区被撑爆了，那么就先检查一下border-sizing是什么，
        最好在引用reset.css的时候，就对border-sizing进行统一设置，方便管理
```
### rem与em的区别
```
    rem是根据根的font-size变化，而em是根据父级的font-size变化
    
    rem：相对于根元素html的font-size，假如html为font-size：12px，那么，在其当中的div设置为font-size：2rem,就是当中的div为24px
    em：相对于父元素计算，假如某个p元素为font-size:12px,在它内部有个span标签，设置font-size：2em,那么，这时候的span字体大小为：12*2=24px

```
### CSS选择器
```
    css常用选择器:
        通配符：*
        ID选择器：#ID
        类选择器：.class
        元素选择器：p、a    等
        后代选择器：p span、div a   等
        伪类选择器：a:hover 等
        属性选择器：input[type="text"]  等
    
    css选择器权重:
        !important -> 行内样式 -> #id -> .class -> 元素和伪元素 -> * -> 继承 -> 默认
    
    CSS新特性:
        transition：过渡
        transform：旋转、缩放、移动或者倾斜
        animation：动画
        gradient：渐变
        shadow：阴影
        border-radius：圆角
```

### 行内元素和块级元素
```
    行内元素（display: inline）:
        宽度和高度是由内容决定，与其他元素共占一行的元素，我们将其叫行内元素，例如：<span> 、 <i> 、 <a>等
    块级元素（display: block):
        默认宽度由父容器决定，默认高度由内容决定，独占一行并且可以设置宽高的元素，我们将其叫做块级元素，例如：<p> 、<div> 、<ul>等
    在平时，我们经常使用CSS的display: inline-block，使它们拥有更多的状态


```
### 绝对定位和相对定位的区别
```
    position: absolute：
        绝对定位：是相对于元素最近的已定位的祖先元素

    position: relative:
        相对定位：相对定位是相对于元素在文档中的初始位置
```
### Flex布局
```
    什么是flex布局？
        Flex是Flexible Box的缩写，意味"弹性布局"，任何一个容器都可以指定为Flex布局
        
    flex的基本概念？
        Flex布局元素，称为Flex容器，简称"容器"。它的所有子元素自动成为容器元素，简称"项目"。
        容器默认存在两根轴：水平的主轴(main axis)和垂直的交叉轴(cross axis)。主轴的排列方式：从左到右；交叉轴的排列方式：从上到下;
        
    容器的属性:
        1、flex-direction :属性决定主轴的方向 (即项目的排列方式）
            flex-direction：row （主轴水平方向，起点在左端）
            flex-direction：row-reverse （主轴水平方向，起点在右端）
            flex-direction：column （主轴垂直方向，起点在上沿）
            flex-direction：column-reverse （主轴在垂直方向，起点在下沿）
        
        2、flex-wrap : 默认情况下，项目都排在一条线（又称"轴线"上）
            flex-wrap：nowarp （不换行，默认的)
            flex-wrap：wrap （换行，第一行在上面）
            flex-wrap：wrap-reverse （换行，第一行在下面）
            
        3、flex-flow：是flex-direction 属性和flex-wrap属性的简写，默认值row、nowrap
        
        4、justify-content：属性定义了项目在主轴上的对齐方式
            justify-content：flex-start （左对齐，默认值）
            justify-content：flex-end（右对齐）
            justify-content：center （居中）
            justify-content：space-between （两端对齐，项目之间的间隔相等）
            justify-content：space-around （每个项目两侧的间距相等）
            
        5、align-items :定义项目交叉轴上如何对齐（单行）
            align-items：flex-start （交叉轴起点对齐）
            align-items: flex-end （交叉轴终点对齐）
            align-items：center （垂直方向，中间开始）
            align-items：baseline （项目第一行文字的基线对齐）
            align-items：stretch （默认值，如果项目未设置高度或设为auto,将占满整个容器的高度)
        
        6、align-content :多行轴线对齐（用法同align-items ）
        
    flex项目属性:
        1、order 定义项目排列顺序
            order：number （数值越小越靠前，默认为0）
        
        2、flex-grow 定义项目放大比例
            flex-grow ：number（默认0，如果有剩余空间也不放大，值为1放大，2是1的双倍大小，此类推）
        
        3、flex-shrink 定义项目缩小比例
            flex-shrink ：number （默认为1，如果空间不足则会缩小，值为0不能缩小）
            
        4、flex-basis 定义项目自身大小
            flex-basis ：number/auto （默认auto，可设置固定的值50px/50%）
            
        5、flex：属性是flex-grow，flex-shrink ,flex-basis的简写，默认值为0、1、auto
        
         6、align-self 项目自身对齐
            align-self ：auto | flex-start | flex-end | center | baseline | stretch
```

### less,sass,styus三者的区别
```
    变量:

        Sass声明变量必须是『$』开头，后面紧跟变量名和变量值，而且变量名和变量值需要使用冒号：分隔开。
        Less 声明变量用『@』开头，其余等同 Sass。
        Stylus 中声明变量没有任何限定，结尾的分号可有可无，但变量名和变量值之间必须要有『等号』。

    作用域

        Sass：三者最差，不存在全局变量的概念
        Less：最近的一次更新的变量有效，并且会作用于全部的引用！
        Stylus：Sass 的处理方式和 Stylus 相同，变量值输出时根据之前最近的一次定义计算，每次引用最近的定义有效；
    
    嵌套
        三种 css 预编译器的「选择器嵌套」在使用上来说没有任何区别，甚至连引用父级选择器的标记 & 也相同
    
    继承
        Sass和Stylus的继承非常像，能把一个选择器的所有样式继承到另一个选择器上。使用『@extend』开始，后面接被继承的选择器。Stylus 的继承方式来自 Sass，两者如出一辙。 Less 则又「独树一帜」地用伪类来描述继承关系；
      
    总结
        Sass和Less语法严谨、Stylus相对自由。因为Less长得更像 css，所以它可能学习起来更容易。
        Sass 和 Compass、Stylus 和 Nib 都是好基友。
        Sass 和 Stylus 都具有类语言的逻辑方式处理：条件、循环等，而 Less 需要通过When等关键词模拟这些功能，这方面 Less 比不上 Sass 和 Stylus

```
### link与@import区别与选择
```
    <style type="text/css">
	@import url(CSS文件路径地址)</style>
    <link href="CSSurl路径" rel="stylesheet" type="text/css" /
    
    link功能较多，可以定义 RSS，定义 Rel 等作用，而@import只能用于加载 css；
    当解析到link时，页面会同步加载所引的 css，而@import所引用的 css 会等到页面加载完才被加载；
    @import需要 IE5 以上才能使用；
    link可以使用 js 动态引入，@import不行


```
### 多行元素的文本省略号
```
    overflow : hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical
```
# JavaScript
### JS的几条基本规范
```
    1、不要在同一行声明多个变量
    2、请使用===/！==来比较true/false或者数值
    3、使用对象字面量替代new Array这种形式
    4、不要使用全局变量
    5、Switch语句必须带有default分支
    6、函数不应该有时候有返回值，有时候没有返回值
    7、For循环必须使用大括号
    8、IF语句必须使用大括号
    9、for-in循环中的变量 应该使用var关键字明确限定作用域，从而避免作用域污染

```
### js引用方法
```
    行内引入
        <body>
          <input type="button" onclick="alert('行内引入')" value="按钮"/>
          <button onclick="alert(123)">点击我</button>
        </body>
    内部引入

        <script>
          window.onload = function() {
            alert("js 内部引入！");
          }
        </script>

    外部引入
        <body>
          <div></div>
        
          <script type="text/javascript" src="./js/index.js"></script>
        </body>
        
    注意
        1，不推荐写行内或者HTML中插入<script>,因为浏览器解析顺序缘故，如果解析到死循环之类的JS代码，会卡住页面
        2，建议在onload事件之后，即等HTML、CSS渲染完毕再执行代码

```
### JS的基本数据类型
```
    Undefined、Null、Boolean、Number、String、新增:Symbol
```
### 数组操作
```
    map: 遍历数组，返回回调返回值组成的新数组
    forEach: 无法break，可以用try/catch中throw new Error来停止
    filter: 过滤
    some: 有一项返回true，则整体为true
    every: 有一项返回false，则整体为false
    join: 通过指定连接符生成字符串
    push / pop: 末尾推入和弹出，改变原数组， 返回推入/弹出项【有误】
    unshift / shift: 头部推入和弹出，改变原数组，返回操作项【有误】
    sort(fn) / reverse: 排序与反转，改变原数组
    concat: 连接数组，不影响原数组， 浅拷贝
    slice(start, end): 返回截断后的新数组，不改变原数组
    splice(start, number, value...): 返回删除元素组成的数组，value 为插入项，改变原数组
    indexOf / lastIndexOf(value, fromIndex): 查找数组项，返回对应的下标
    reduce / reduceRight(fn(prev, cur)， defaultPrev): 两两执行，prev 为上次化简函数的return值，cur 为当前值(从第二项开始)

```

### JS有哪些内置对象
```
    Object是JavaScript中所有对象的父对象
    数据封装对象：Object、Array、Boolean、Number和String
    其他对象：Function、Arguments、Math、Date、RegExp、Error
```
### get请求传参长度的误区和区别
```
    误区：我们经常说get请求参数的大小存在限制，而post请求的参数大小是无限制的
    实际上HTTP 协议从未规定 GET/POST 的请求长度限制是多少。对get请求参数的限制是来源与浏览器或web服务器，浏览器或web服务器限制了url的长度。为了明确这个概念，我们必须再次强调下面几点:
    1、HTTP 协议 未规定 GET 和POST的长度限制
    2、GET的最大长度显示是因为 浏览器和 web服务器限制了 URI的长度
    3、不同的浏览器和WEB服务器，限制的最大长度不一样
    4、要支持IE，则最大长度为2083byte，若只支持Chrome，则最大长度 8182byte
    
    区别:
        get请求类似于查找的过程，用户获取数据，可以不用每次都与数据库连接，所以可以使用缓存。

        post不同，post做的一般是修改和删除的工作，所以必须与数据库交互，所以不能使用缓存。因此get请求适合于请求缓存。
```
### 闭包
```
    什么是闭包？

        函数A 里面包含了 函数B，而 函数B 里面使用了 函数A 的变量，那么 函数B 被称为闭包。
        
        又或者：闭包就是能够读取其他函数内部变量的函数
        
        function A() {
          var a = 1;
          function B() {
            console.log(a);
          }
          return B();
        }
    
        闭包的特征:
            函数内再嵌套函数
            内部函数可以引用外层的参数和变量
            参数和变量不会被垃圾回收制回收
        
        对闭包的理解：
            使用闭包主要是为了设计私有的方法和变量。闭包的优点是可以避免全局变量的污染，缺点是闭包会常驻内存，会增大内存使用量，使用不当很容易造成内存泄露。在js中，函数即闭包，只有函数才会产生作用域的概念
            闭包 的最大用处有两个，一个是可以读取函数内部的变量，另一个就是让这些变量始终保持在内存中
            闭包的另一个用处，是封装对象的私有属性和私有方法

        闭包的好处:能够实现封装和缓存等

        闭包的坏处:就是消耗内存、不正当使用会造成内存溢出的问题
        
        使用闭包的注意点:
            由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，
            否则会造成网页的性能问题，在IE中可能导致内存泄露
            解决方法是：在退出函数之前，将不使用的局部变量全部删除
```

### JS作用域及作用域链
```
    在JavaScript中，作用域分为 全局作用域 和 函数作用域
    
    全局作用域:
        代码在程序的任何地方都能被访问，window 对象的内置属性都拥有全局作用域  
    
    函数作用域
        在固定的代码片段才能被访问
    
    作用域有上下级关系，上下级关系的确定就看函数是在哪个作用域下创建的。如上，fn作用域下创建了bar函数，那么“fn作用域”就是“bar作用域”的上级。
    作用域最大的用处就是隔离变量，不同作用域下同名变量不会有冲突。
    变量取值：到创建 这个变量 的函数的作用域中取值

    作用域链

        一般情况下，变量取值到 创建 这个变量 的函数的作用域中取值。

        但是如果在当前作用域中没有查到值，就会向上级作用域去查，直到查到全局作用域，
        这么一个查找过程形成的链条就叫做作用域链
```

### 原型和原型链
```
    原型和原型链的概念
        每个对象都会在其内部初始化一个属性，就是prototype(原型)，当我们访问一个对象的属性时，如果这个对象内部不存在这个属性，那么他就会去prototype里找这个属性，这个prototype又会有自己的prototype，于是就这样一直找下去
    
    原型和原型链的关系
        instance.constructor.prototype = instance.__proto__
    
    原型和原型链的特点
        JavaScript对象是通过引用来传递的，我们创建的每个新对象实体中并没有一份属于自己的原型副本。当我们修改原型时，与之相关的对象也会继承这一改变
        当我们需要一个属性的时，Javascript引擎会先看当前对象中是否有这个属性， 如果没有的
        就会查找他的Prototype对象是否有这个属性，如此递推下去，一直检索到 Object 内建对象


```
### 组件化和模块化
```

    组件化
        为什么要组件化开发
        有时候页面代码量太大，逻辑太多或者同一个功能组件在许多页面均有使用，维护起来相当复杂，这个时候，就需要组件化开发来进行功能拆分、组件封装，已达到组件通用性，增强代码可读性，维护成本也能大大降低
        组件化开发的优点
        很大程度上降低系统各个功能的耦合性，并且提高了功能内部的聚合性。这对前端工程化及降低代码的维护来说，是有很大的好处的，耦合性的降低，提高了系统的伸展性，降低了开发的复杂度，提升开发效率，降低开发成本

    组件化开发的原则

        专一
    
        可配置性
        
        标准性
        
        复用性
        
        可维护性


    模块化
        为什么要模块化
        早期的javascript版本没有块级作用域、没有类、没有包、也没有模块，这样会带来一些问题，如复用、依赖、冲突、代码组织混乱等，随着前端的膨胀，模块化显得非常迫切
        模块化的好处


        避免变量污染，命名冲突
        
        
        提高代码复用率
        
        
        提高了可维护性
        
        
        方便依赖关系管理
        
        
        模块化的几种方法
            函数封装
            立即执行函数表达式(IIFE)

```
### 图片的预加载和懒加载
```
    预加载：提前加载图片，当用户需要查看时可直接从本地缓存中渲染
    懒加载：懒加载的主要目的是作为服务器前端的优化，减少请求数或延迟请求数


    两种技术的本质：两者的行为是相反的，一个是提前加载，一个是迟缓甚至不加载。预加载则会增加服务器前端压力，懒加载对服务器有一定的缓解压力作用。


```
### mouseover和mouseenter的区别
```
    mouseover：当鼠标移入元素或其子元素都会触发事件，所以有一个重复触发，冒泡的过程。对应的移除事件是mouseout

    mouseenter：当鼠标移除元素本身（不包含元素的子元素）会触发事件，也就是不会冒泡，对应的移除事件是mouseleave
```
### 解决异步回调地狱
```
    promise、generator、async/await
```
### 对This对象的理解
```
    this总是指向函数的直接调用者（而非间接调用者）
    如果有new关键字，this指向new出来的那个对象
    
    在事件中，this指向触发这个事件的对象，特殊的是，IE中的attachEvent中的this总是指向全局对象Window
```
## Vue

### vue生命周期
```
    什么是Vue生命周期？
        Vue 实例从创建到销毁的过程，就是生命周期。也就是从开始创建、初始化数据、编译模板、挂载Dom→渲染、更新→渲染、卸载等一系列过程，我们称这是 Vue 的生命周期
    Vue生命周期的作用是什么？
        它的生命周期中有多个事件钩子，让我们在控制整个Vue实例的过程时更容易形成好的逻辑
    Vue生命周期总共有几个阶段？
        它可以总共分为8个阶段：创建前/后, 载入前/后,更新前/后,销毁前/销毁后
    第一次页面加载会触发哪几个钩子？
        第一次页面加载时会触发 beforeCreate, created, beforeMount, mounted 这几个钩子
    DOM渲染在哪个周期中就已经完成？
        DOM 渲染在 mounted 中就已经完成了
    每个生命周期适合哪些场景？
        生命周期钩子的一些使用方法：
        beforecreate : 可以在这加个loading事件，在加载实例时触发
        created : 初始化完成时的事件写在这里，如在这结束loading事件，异步请求也适宜在这里调用
        mounted : 挂载元素，获取到DOM节点
        updated : 如果对数据统一处理，在这里写上相应函数
        beforeDestroy : 可以做一个确认停止事件的确认框
        nextTick : 更新数据后立即操作dom

```
### v-show与v-if区别
```
    v-show是css切换，v-if是完整的销毁和重新创建
    使用 频繁切换时用v-show，运行时较少改变时用v-if
    
    v-if=‘false’ v-if是条件渲染，当false的时候不会渲染
```
### 开发中常用的指令有哪些
```
    v-model :一般用在表达输入，很轻松的实现表单控件和数据的双向绑定
    v-html: 更新元素的 innerHTML
    v-show 与 v-if: 条件渲染, 注意二者区别

    使用了v-if的时候，如果值为false，那么页面将不会有这个html标签生成
    v-show则是不管值为true还是false，html元素都会存在，只是CSS中的display显示或隐藏

    v-on : click: 可以简写为@click,@绑定一个事件。如果事件触发了，就可以指定事件的处理函数
    v-for:基于源数据多次渲染元素或模板块
    v-bind: 当表达式的值改变时，将其产生的连带影响，响应式地作用于 DOM

    语法：v-bind:title="msg" 简写：:title="msg"


```
### 绑定class的数组用法
```
    对象方法 v-bind:class="{'orange': isRipe, 'green': isNotRipe}"
    数组方法  v-bind:class="[class1, class2]"
    行内 v-bind:style="{color: color, fontSize: fontSize+'px' }"


```
### 组件之间的传值通信
```
    父组件给子组件传值

    使用props，父组件可以使用props向子组件传递数据

    父组件vue模板father.vue
    <template>
        <child :msg="message"></child>
    </template>
    
    <script>
    import child from './child.vue';
    export default {
        components: {
            child
        },
        data () {
            return {
                message: 'father message';
            }
        }
    }
    </script>

    子组件vue模板child.vue:
    <template>
        <div>{{msg}}</div>
    </template>
    
    <script>
    export default {
        props: {
            msg: {
                type: String,
                required: true
            }
        }
    }
    </script>
    
    子组件向父组件通信

    父组件向子组件传递事件方法，子组件通过$emit触发事件，回调给父组件

    父组件vue模板father.vue:
    <template>
        <child @msgFunc="func"></child>
    </template>
    
    <script>
    import child from './child.vue';
    export default {
        components: {
            child
        },
        methods: {
            func (msg) {
                console.log(msg);
            }
        }
    }
    </script>

    子组件vue模板child.vue:
    <template>
        <button @click="handleClick">点我</button>
    </template>
    
    <script>
    export default {
        props: {
            msg: {
                type: String,
                required: true
            }
        },
        methods () {
            handleClick () {
                //........
                this.$emit('msgFunc');
            }
        }
    }
    </script>


    非父子，兄弟组件之间通信
    
    可以通过实例一个vue实例Bus作为媒介，要相互通信的兄弟组件之中，都引入Bus，然后通过分别调用Bus事件触发和监听来实现通信和参数传递
    
    Bus.js可以是这样:
    
        import Vue from 'vue'
        export default new Vue()
    
    在需要通信的组件都引入Bus.js:
        <template>
        	<button @click="toBus">子组件传给兄弟组件</button>
        </template>
        
        <script>
        import Bus from '../common/js/bus.js'
        export default{
        	methods: {
        	    toBus () {
        	        Bus.$emit('on', '来自兄弟组件')
        	    }
        	  }
        }
        </script>
        
    另一个组件也import Bus.js 在钩子函数中监听on事件
    import Bus from '../common/js/bus.js'
    export default {
        data() {
          return {
            message: ''
          }
        },
        mounted() {
           Bus.$on('on', (msg) => {
             this.message = msg
           })
         }
       }

```
### 路由跳转方式
```
    1，<router-link to='home'> router-link标签会渲染为<a>标签，咋填template中的跳转都是这种；

    2，另一种是编程是导航 也就是通过js跳转 比如 router.push('/home')
```
### MVVM
```
    M - Model，Model 代表数据模型，也可以在 Model 中定义数据修改和操作的业务逻辑
    
    V - View，View 代表 UI 组件，它负责将数据模型转化为 UI 展现出来
    
    VM - ViewModel，ViewModel 监听模型数据的改变和控制视图行为、处理用户交互，简单理解就是一个同步 View 和 Model 的对象，连接 Model 和 View


```
### computed和watch有什么区别?
```
    computed:
        1. computed是计算属性,也就是计算值,它更多用于计算值的场景
        2. computed具有缓存性,computed的值在getter执行后是会缓存的，只有在它依赖的属性值改变之后，下一次获取computed的值时才会重新调用对应的getter来计算
        3. computed适用于计算比较消耗性能的计算场景
    
    watch:
        1. 更多的是「观察」的作用,类似于某些数据的监听回调,用于观察props $emit或者本组件的值,当数据变化时来执行回调进行后续操作
        2. 无缓存性，页面重新渲染时值不变化也会执行
        
    小结:
        1. 当我们要进行数值计算,而且依赖于其他数据，那么把这个数据设计为computed
        2. 如果你需要在某个数据变化时做一些事情，使用watch来观察这个数据变化

```
### key
```
    key是为Vue中的vnode标记的唯一id，通过这个key，我们的diff操作可以 更准确、更快速
    准确:
        如果不加key,那么vue会选择复用节点(Vue的就地更新策略),导致之前节点的状态被保留下来，会产生一系列的bug

    快速:
        key的唯一性可以被Map数据结构充分利用
```
### 组件中的data为什么是函数？
```
    为什么组件中的data必须是一个函数，然后return一个对象，而new Vue实例里，data可以直接是一个对象？
        因为组件是用来复用的，JS里对象是引用关系，这样作用域没有隔离，而new Vue的实例，是不会被复用的，因此不存在引用对象问题
    
```
### keep-alive
``` 
    keep-alive 是 Vue 内置的一个组件，可以使被包含的组件保留状态，避免重新渲染 ，其有以下特性：
    一般结合路由和动态组件一起使用，用于缓存组件；
    提供 include 和 exclude 属性，两者都支持字符串或正则表达式， include 表示只有名称匹配的组件会被缓存，exclude 表示任何名称匹配的组件都不会被缓存 ，其中 exclude 的优先级比 include 高；
    对应两个钩子函数 activated 和 deactivated ，当组件被激活时，触发钩子函数 activated，当组件被移除时，触发钩子函数 deactivated。


```
### nextTick()
```
    在下次DOM更新循环结束之后执行延迟回调。在修改数据之后，立即使用的这个回调函数，获取更新后的DOM
```

### vue-router有哪几种导航钩子
```
    第一种：是全局导航钩子：router.beforeEach(to,from,next)，作用：跳转前进行判断拦截

    第二种：组件内的钩子
    
    第三种：单独路由独享组件
```
### vuex
```
    vuex 就是一个仓库，仓库里放了很多对象。其中 state 就是数据源存放地，对应于一般 vue 对象里面的 data

    state 里面存放的数据是响应式的，vue 组件从 store 读取数据，若是 store 中的数据发生改变，依赖这相数据的组件也会发生更新
    
    它通过 mapState 把全局的 state 和 getters 映射到当前组件的 computed 计算属性
    
    Vuex有5种属性: 分别是 state、getter、mutation、action、module;
    
    state
    Vuex 使用单一状态树,即每个应用将仅仅包含一个store 实例，但单一状态树和模块化并不冲突。存放的数据状态，不可以直接修改里面的数据
    
    mutations
    mutations定义的方法动态修改Vuex 的 store 中的状态或数据
    
    getters
    类似vue的计算属性，主要用来过滤一些数据
    
    action
    actions可以理解为通过将mutations里面处里数据的方法变成可异步的处理数据的方法，简单的说就是异步操作数据。view 层通过 store.dispath 来分发 action
    
    总结
        vuex 一般用于中大型 web 单页应用中对应用的状态进行管理，对于一些组件间关系较为简单的小型应用，使用 vuex 的必要性不是很大，因为完全可以用组件 prop 属性或者事件来完成父子组件之间的通信，vuex 更多地用于解决跨组件通信以及作为数据中心集中式存储数据



```
### 你有对 Vue 项目进行哪些优化？
```

    代码层面的优化
        v-if 和 v-show 区分使用场景
        computed 和 watch  区分使用场景
        v-for 遍历必须为 item 添加 key，且避免同时使用 v-if
        长列表性能优化
        事件的销毁
        图片资源懒加载
        路由懒加载
        第三方插件的按需引入
        优化无限列表性能
        服务端渲染 SSR or 预渲染
    
    Webpack 层面的优化
        Webpack 对图片进行压缩
        减少 ES6 转为 ES5 的冗余代码
        提取公共代码
        模板预编译
        提取组件的 CSS
        优化 SourceMap
        构建结果输出分析
        Vue 项目的编译优化
    
    基础的 Web 技术的优化
        开启 gzip 压缩
        浏览器缓存
        CDN 的使用
        使用 Chrome Performance 查找性能瓶颈


```
## ES6
### var、let、const之间的区别
```
    var声明变量可以重复声明，而let不可以重复声明
    var是不受限于块级的，而let是受限于块级
    var会与window相映射（会挂一个属性），而let不与window相映射
    var可以在声明的上面访问变量，而let有暂存死区，在声明的上面访问变量会报错
    const声明之后必须赋值，否则会报错
    const定义不可变的量，改变了就会报错
    const和let一样不会与window相映射、支持块级作用域、在声明的上面访问变量会报错


```
### 解构赋值
```
    数组解构
        let [a, b, c] = [1, 2, 3]   //a=1, b=2, c=3
        let [d, [e], f] = [1, [2], 3]    //嵌套数组解构 d=1, e=2, f=3
        let [g, ...h] = [1, 2, 3]   //数组拆分 g=1, h=[2, 3]
        let [i,,j] = [1, 2, 3]   //不连续解构 i=1, j=3
        let [k,l] = [1, 2, 3]   //不完全解构 k=1, l=2
    
    对象解构
        let {a, b} = {a: 'aaaa', b: 'bbbb'}      //a='aaaa' b='bbbb'
        let obj = {d: 'aaaa', e: {f: 'bbbb'}}
        let {d, e:{f}} = obj    //嵌套解构 d='aaaa' f='bbbb'
        let g;
        (g = {g: 'aaaa'})   //以声明变量解构 g='aaaa'
        let [h, i, j, k] = 'nice'    //字符串解构 h='n' i='i' j='c' k='e'
    
    函数参数的定义
        一般我们在定义函数的时候，如果函数有多个参数时，在es5语法中函数调用时参数必须一一对应，否则就会出现赋值错误的情况，来看一个例子：
        function personInfo(name, age, address, gender) {
          console.log(name, age, address, gender)
        }
        personInfo('william', 18, 'changsha', 'man')
        上面这个例子在对用户信息的时候需要传递四个参数，且需要一一对应，这样就会极易出现参数顺序传错的情况，从而导致bug，接下来来看es6解构赋值是怎么解决这个问题的：
        function personInfo({name, age, address, gender}) {
          console.log(name, age, address, gender)
        }
        personInfo({gender: 'man', address: 'changsha', name: 'william', age: 18})
        这么写我们只知道要传声明参数就行来，不需要知道参数的顺序也没关系

   交换变量的值
       在es5中我们需要交换两个变量的值需要借助临时变量的帮助，来看一个例子：
        var a=1, b=2, c
        c = a
        a = b
        b = c
        console.log(a, b)
        来看es6怎么实现：
        let a=1, b=2;
        [b, a] = [a, b]
        是不是比es5的写法更加方便呢

```
### forEach、for in、for of三者区别
```
    forEach更多的用来遍历数
    for in 一般常用来遍历对象或json
    
    for of数组对象都可以遍历，遍历对象需要通过和Object.keys()
    
    for in循环出的是key，for of循环出的是value
```
### 使用箭头函数应注意什么？
```
    1、用了箭头函数，this就不是指向window，而是父级（指向是可变的）
    2、不能够使用arguments对象
    3、不能用作构造函数，这就是说不能够使用new命令，否则会抛出一个错误
    4、不可以使用yield命令，因此箭头函数不能用作 Generator 函数


```
### Set、Map的区别
```
    应用场景Set用于数据重组，Map用于数据储存

    Set：
    1，成员不能重复
    2，只有键值没有键名，类似数组
    3，可以遍历，方法有add, delete,has
    
    Map:
    1，本质上是健值对的集合，类似集合
    2，可以遍历，可以跟各种数据格式转换
```
### promise对象的用法,手写一个promise
```
    var promise = new Promise((resolve,reject) => {
        if (操作成功) {
            resolve(value)
        } else {
            reject(error)
        }
    })
    promise.then(function (value) {
        // success
    },function (value) {
        // failure
    })




```
## webpack
### webpack打包原理
```
    webpack只是一个打包模块的机制，只是把依赖的模块转化成可以代表这些包的静态文件。webpack就是识别你的 入口文件。识别你的模块依赖，来打包你的代码。至于你的代码使用的是commonjs还是amd或者es6的import。webpack都会对其进行分析。来获取代码的依赖。webpack做的就是分析代码。转换代码，编译代码，输出代码。webpack本身是一个node的模块，所以webpack.config.js是以commonjs形式书写的(node中的模块化是commonjs规范的)

```
### 如何提高webpack构建速度
```
    1、通过externals配置来提取常用库
    2、利用DllPlugin和DllReferencePlugin预编译资源模块 通过DllPlugin来对那些我们引用但是绝对不会修改的npm包来进行预编译，再通过DllReferencePlugin将预编译的模块加载进来
    3、使用Happypack 实现多线程加速编译
    要注意的第一点是，它对file-loader和url-loader支持不好，所以这两个loader就不需要换成happypack了，其他loader可以类似地换一下
    4、使用Tree-shaking和Scope Hoisting来剔除多余代码
    5、使用fast-sass-loader代替sass-loader
    6、babel-loader开启缓存


```
### webpack的优点
```
    专注于处理模块化的项目，能做到开箱即用，一步到位
    可通过plugin扩展，完整好用又不失灵活
    
    使用场景不局限于web开发
    
    社区庞大活跃，经常引入紧跟时代发展的新特性，能为大多数场景找到已有的开源扩展
    
    良好的开发体验
```
### webpack的缺点
```
    webpack的缺点是只能用于采用模块化开发的项目
```
## 性能优化
### HTML优化
```
    1、避免 HTML 中书写 CSS 代码，因为这样难以维护。
    2、使用 Viewport 加速页面的渲染。
    3、使用语义化标签，减少 CSS 代码，增加可读性和 SEO。
    4、减少标签的使用，DOM 解析是一个大量遍历的过程，减少不必要的标签，能降低遍历的次数。
    5、避免 src、href 等的值为空，因为即时它们为空，浏览器也会发起 HTTP 请求。
    6、减少 DNS 查询的次数


```
### CSS优化
```
    1、优化选择器路径：使用 .c {} 而不是 .a .b .c {}。
    2、选择器合并：共同的属性内容提起出来，压缩空间和资源开销。
    3、精准样式：使用 padding-left: 10px 而不是 padding: 0 0 0 10px。
    4、雪碧图：将小的图标合并到一张图中，这样所有的图片只需要请求一次。
    5、避免通配符：.a .b * {} 这样的选择器，根据从右到左的解析顺序在解析过程中遇到通配符 * {} 6、会遍历整个 DOM，性能大大损耗。
    7、少用 float：float 在渲染时计算量比较大，可以使用 flex 布局。
    8、为 0 值去单位：增加兼容性。
    9、压缩文件大小，减少资源下载负担。

```
### JavaScript优化
```
    1、尽可能把 <script> 标签放在 body 之后，避免 JS 的执行卡住 DOM 的渲染，最大程度保证页面尽快地展示出来
    2、尽可能合并 JS 代码：提取公共方法，进行面向对象设计等……
    3、CSS 能做的事情，尽量不用 JS 来做，毕竟 JS 的解析执行比较粗暴，而 CSS 效率更高。
    4、尽可能逐条操作 DOM，并预定好 CSs 样式，从而减少 reflow 或者 repaint 的次数。
    5、尽可能少地创建 DOM，而是在 HTML 和 CSS 中使用 display: none 来隐藏，按需显示。
    6、压缩文件大小，减少资源下载负担。

```




