# trip

> this is vuejs project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
###项目环境准备

## node环境

## vue环境

    vue  init webpack 项目名

    npm run dev  (start)

## 码云  
   注册账号  
   创建远程仓库 Trip


## 版本管理工具  git

    git命令

    git使用
        git clone  远程仓库地址

        git  status  查看状态

        git  add .  把所有文件放到缓存区

        git  commit -m  "描述" 缓存区到本地仓库

        git  push  推送到远程仓库   

        git pull   从远程仓库拉取代码

        git  branch  查看分支   -r

        git checkout 分支名  切换分支

        vscode中git的使用
            第二项里边：



##  功能需求 
    参考： https://touch.piao.qunar.com/

    首页模块：

    城市模块

    列表详情页模块


### 开发环境统一
    现在在  index-init分支下开发
    统一视口： meta  
    移动端   <meta name="viewport" content="width=device-width,initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0,user-scalable=1.0">


    统一样式：  保证页面在所有浏览器下显示效果一致  
    reset.css  font-size: 50px;

    1px边框像素问题：  手机像素都比较高  如果是2倍 3倍屏  虽然设置border:1px  实际上有 2px  3px
    border.css      解决方案  使用css3 的 scale属性

    300毫秒点击延迟问题：
    fastclick   

    cnpm i fastclick --save

    全局引入   main.js中
    import fastClick  from  "fastclick"
    fastClick.attach(document.body)


    字体图标：https://www.iconfont.cn/
    注册账号  
    创建项目
    添加图标到购物车  添加到项目
    下载项目
    选择文件  配置

    css预处理器   stylus    sass  less我都会用  
    cnpm  i  stylus --save 
    cnpm  i  stylus-loader --save
    语法部分   写的时候
    {}可有可无  
    tab 空格有用


##  正式进入项目开发

    ###  首页模块
        首页：

        Home.vue  及
        子组件   HomeHeader.vue   头部组件

        HomeHeader.vue的开发：
        html部分
            <div class="header">
            <div class="headr-left">
                <div class="iconfont back-icon">&#xe624;</div>
            </div>
            <div class="header-input">
                <span class="iconfont">&#xe61b;</span>
                输入城市/景点/游玩主题
            </div>
            <div class="header-right">
                城市城市
                <span class="iconfont arrow-icon">&#xe62d;</span>
            </div>    
        </div>


        css部分
            .header 
                display : flex
                line-height :.86rem
                background : #00bcd4
                color : #fff 
                .header-left
                    width : .64rem
                    float : left 
                    .back-icon
                        text-align : center
                        font-scale :.4rem
                .header-input
                    flex : 1
                    height : .64rem
                    line-height : .64rem
                    margin-top :.12rem
                    margin-left :.2rem
                    padding-left : .2rem
                    background : #fff 
                    border-radius : .1rem
                    color : #cccccc
                .header-right
                    min-width : 1.04rem
                    padding : 0 .1rem
                    float : right
                    text-align : center
                    color  :  #ffffff
                    arrow-icon
                        margin-left : -.05rem
                        font-size : .24rem

    提交到本地缓存    
    到本地仓库
    推送到远程仓库  
    切换到主分支           git  checkout  master
    合并index-init分支     git  merge  index-init


    轮播图：
    远程仓库 创建分支   index-swiper
    同步到本地                               
    切换到index-swiper开发 轮播图 
    vue-awesom-swiper
    抖动？ 
    





##作业   图片布局    放到码云上去   说明： 

1:  移动端适配问题  ：rem.js  js操作改变  特意避免   reset.css文件   reset.css  font-size: 50px;   1rem = 50px     iphone6  

    1： 移动端适配问题    rem原理  rem.js
    2： 百分比布局
    3： 媒体查询
    4： vw  vh vmax vmin
        .....
    5:  scss  less  封装函数转换

2： vue.js   基础语法 今天讲课带一些上去

3： 码云：  ssh   百度下   配置公钥

4： 使用git   熟练操作   基本命令记住  昨天操作  熟练  多练习  ok 


讲课内容：提交内容
提交的授课内容来安排的：

###  轮播区
    Vue-Awesome-Swiper     start最高

    1: 安装 Vue-Awesome-Swiper 
        npm install vue-awesome-swiper@2.6.7 --save 

    2: Vue-Awesome-Swiper  spa中使用
       vue.js    main.js中
       import VueAwesomeSwiper from 'vue-awesome-swiper'
        import 'swiper/dist/css/swiper.css'
        Vue.use(VueAwesomeSwiper)
    3: 页面中应用

        <div>
            <swiper :options="swiperOption" >
                <swiper-slide>
                    <img src="http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg" alt="">
                </swiper-slide>
                <swiper-slide>
                    <img src="http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg" alt="">
                </swiper-slide>       
                <div class="swiper-pagination"  slot="pagination"></div>
                
            </swiper>
        </div>


    布局有问题 ：   页面会抖动：
    swiper区域 没有加载的时候 为0  加载后马上撑开图片区域大小  对于后边的元素会产生抖动的现象
    需要处理：
    外边加盒子
    第一种
    .wrapper
        overflow : hidden
        width : 100%
        height : 0
        padding-bottom : 31.25%
        // background : red
        
    第二种
        background : red
        height :31.25vw


    样式穿透问题：
    scoped   只在组件范围内
     .wrapper >>> .swiper-pagination-bullet-active
        background  : #fff

    在vue中数组的遍历
    v-for="item of array"  

    ajax获取数据  数组暂存   遍历



###  图标区域的页面布局
    创建组件   Icons.vue
    页面布局：
    <div class="icons">
        <div class="icon">
        </div>
    </div>

    .icons  
        overflow : hidden
        height : 0
        padding-bottom : 50%
        background : green 
        .icon
            float : left
            width : 25%
            padding-bottom : 25%
            background : red

    
    去掉 overflow : hidden  swiper自带  
    页面逻辑：

    丢失了一个数据
    解决：
    computed:   计算属性    页码
    分页概念：
        computed : {
            pages(){//二维数组
                const pages = []
                this.iconList.forEach((item,index)=>{
                    //page页码  当前下标的数据应该在轮播图的第几页 index为3 下标是2  Math.floor(（1-8） / 8)   第一页
                    const page = Math.floor(index / 8)
                    if (!pages[page]) {
                        pages[page] = []
                    }
                    pages[page].push(item)  //二维数组里边的一维数组
                })
                return pages
            }
        },



    安装vuejs的开发帮助工具：
       vue  devtools


    css3  内容
    ... 
    overflow : hidden
    white-space : nowrap
    text-overflow : ellipsis

    在stylus中封装方法
        创建一个后缀名为.styl
        ellipsis()
            overflow : hidden
            white-space : nowrap
            text-overflow : ellipsis
        在组件的地方
            导入.styl
             @import "../../../assets/styles/mixins.styl"
             使用功能的地方
              ellipsis()


###   作业：   stylus   组件  
    1：布局：  练习下我刚讲的布局方式
       图片轮播
       九宫格布局

    2：九宫格逻辑实现 

    3：做下热销推荐的  （可做可不做）



#### 第三天内容：
    ###  Recommend.vue 热销组件   布局：  仓库也更新好了   pull下来
    数据：Model 
    data:(){}
    v-for="(item,index) in 遍历的对象或数组"
    静态渲染的内容 -》 Model里数组的内容
    v-bind:属性= ""
    {{}}  插值表达式

    border.css   1边框像素解决方案
    怎么用：
    类样式中：   border-bottom  border-top   border-left   border-right





    ###WeekEnd.vue  周末旅游组件：布局：  仓库也更新好了   pull下来
    静态渲染的内容 -》 Model里数组的内容
    数据：Model 
    data:(){}
    v-for="(item,index) in 遍历的对象或数组"


    组件化 ：
    Home.vue  父组件   
    HomeHeader.vue  子组件
    Icons.vue     子组件  
    Recommend.vue子组件
    Swiper.vue子组件
    WeekEnd.vue子组件




    ###Ajax获取首页数据：
    Home.vue  父组件    获取数据   减少http请求次数   优化

    vue-cli中：
    原生Ajax:     XmlHttpRequest对象
    fetch         ES6               建议大家使用下fetch 
    vue-resource  停止更新了    跨域请求方式   （.jsonp）  百度接口
    axios         推荐的方式    不支持跨域      用这种方式

    axios:   http请求库  请求方式： get  post  put delete  ...  

    cnpm  install axios --save

    使用：

    单组件使用 ：
    import   axios from "axios"


    全局配置    main.js


    static目录里边的内容可以在脚手架里边直接访问   
    http://localhost:8080/static/mock/index.json

    跨域请求数据的时候   /api
    在vue-cli中配置转发  代理
    config目录下index.js

    proxyTable: {
      '/api' : {
        target :' http://localhost:8080',
        pathRewrite : {
          '^/api' : '/static/mock'
        }
      }
    },
    请求api的时候  proxyTable帮助我们把请求转发道目标地址  http://localhost:8080
    路径做了个替换  一旦请求地址是 api开头  就把它请求替换为  /static/mock
    webpack里边   webpack-server-dev

    配置完成  重新启动脚手架

    获取到数据：
        methods : {
            getHomeInfo(){
                axios.get("/api/index.json")    
                .then(this.getHomeInfoSucc)
            },
            getHomeInfoSucc(res){
                console.log(res)
                res = res.data
                if (res.ret && res.data) {
                    const data = res.data
                    this.city = data.city
                    this.swiperList = data.swiperList
                    this.iconList = data.iconList
                    this.recommendList = data.recommendList
                    this.weekendList = data.weekendList

                }
            }
        },
        mounted (){
            this.getHomeInfo();
        }
    
    通过父子组件通信  把数据传给子组件  子组件在遍历渲染
    父组件中   通过绑定属性传值
    <HomeHeader :city="city"></HomeHeader>
    <HomeSwiper :swiperList="swiperList"></HomeSwiper>
    <HomeIcons :iconList="iconList"></HomeIcons>
    <HomeRecommend :recommendList="recommendList"></HomeRecommend>
    <HomeWeekEnd :weekendList="weekendList"></HomeWeekEnd>

    子组价接受：
    HomeHeader.vue
     props : {
        city : String
    }

    {{ this.city }}


    Swiper.vue
    props: {
        swiperList : Array
    },


    Icons.vue中
    props : {
        iconList : Array
    },


    在Recommend.vue中
    props : {
        recommendList : Array
    },


    在WeekEnd.vue中  
    props : {
        weekendList : Array
    },


    写作业写到这了: 看下bug
    1：图片轮播区：Swiper.vue

       默认显示的图片是最后一张图片   ？
    当swiper加载的时候   swiperList是空数组
    还没ajax获取到数据：当ajax获取到数据后  在存到数组中  造成了这种默认显示的图片是最后一张图片：

    解决的办法：
    swiper应该由完整的数据创建  而不应该是空数组创建
    v-if="swiperList.length"


    是解决问题了  但是还有问题   这种写法不推荐  不优雅  尽量在html部分写逻辑的代码
     computed : {
        showSwiper (){
            return this.swiperList.length
        }
    },

    v-if="showSwiper"


    2：icons区在主动轮播？  这不是我们想要的

    停止自动轮播：
    观察：
     <swiper> </swiper>
    :options="swiperOption"   没有写配置项


    3:Swiper.vue中   如果图片的宽高比发生变化：

    overflow : hidden
    width : 100%
    height : 0
    padding-bottom : 31.25%     
 
    200/640 = 31.25%    要改成具体的比较值
    
       





























