<template>
    <div>
        <div class="title">
            热销推荐
        </div>
        <ul>
            <li class="item border-bottom" v-for="(item,index) in recommendList" :key="index">               
                <img class="item-img"  :src="item.imgUrl" />    
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc"> {{ item.desc }}</p>
                    <button class="item-button">查看详情</button>
                </div>               
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name : "Recommend",
        props : {
            recommendList : Array
        },
        data(){
            return {
                // recommendList:[{
                //     id:"0001",
                //     imgUrl:"http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg",
                //     title:"八达岭长城",
                //     desc:"中国第一长城,中国人一生至少要来一次长城，感受长城没来所在，感受古代文化遗产的伟大"
                // },{
                //     id:"0002",
                //     imgUrl:"http://img1.qunarzz.com/sight/p0/1603/85/85c883189bf7293390.water.jpg_200x200_3165123d.jpg",
                //     title:"什刹海",
                //     desc:"北京的街道就是在市区的人群集结地，在这里有四合院有三轮车有小吃店还有外地的热心游客，因为人们为了体会京城的生活而来，所以想看的是北京老百姓的街道。"
                // },{
                //     id:"0003",
                //     imgUrl:"http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg",
                //     title:"北京野生动物园",
                //     desc:"很大，开车逛了一圈后又步行逛了一圈，小朋友一直想看看长颈鹿，因为天冷关起来了，没看到。看到了网红的老虎，狮子，狗兄一家子，但没看到狗妈妈。一袋小油菜，胡萝卜等叶菜要30元🙀不过小朋友喂鹿很开心！不过建议大家还是别冬天去，少见不少！"
                // },{
                //     id:"0004",
                //     imgUrl:"http://img1.qunarzz.com/sight/p0/1607/ce/ce94534274b3bd6db4.water.jpg_200x200_91a2f180.jpg",
                //     title:"清华大学",
                //     desc:"自由发挥。行程安排合理，导游讲解专业，微笑服务。司机师傅技术好，待人和气，游玩八达岭长城，颐和园，还路过了清华大学一路玩得开心，这次旅游真的使我开心快乐。"
                // },{
                //     id:"0005",
                //     imgUrl:"http://img1.qunarzz.com/sight/p0/1602/92/920e47352552c1c990.water.jpg_200x200_dba18b05.jpg",
                //     title:"天坛公园",
                //     desc:"北京天坛公园一个古树成林、古迹成片，北京这个景区深受各地游客的喜爱。既有古树，又有古建筑的天坛公园，是一个天然大氧吧。也是北京市民晨练的最佳去处……"
                // }]
            }
        }
    }
</script>

<style lang="stylus" scoped>
@import "../../../assets/styles/mixins.styl"

.title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
.item
    overflow: hidden
    display: flex
    height: 1.9rem
    // background :red
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff



</style>