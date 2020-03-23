
<template>
    <div class="header">
        <div class="headr-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe61b;</span>
            输入城市/景点/游玩主题
        </div>
        <div class="header-right">
            {{ this.city }}
            <span class="iconfont arrow-icon">&#xe62d;</span>
        </div>    
    </div>
</template>

<script>
    export default {
        name : "HomeHeader",
        props : {
            city : String
        }
    }
</script>

<style lang="stylus" scoped>

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







</style>
