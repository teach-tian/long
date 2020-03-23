
<template>
    <div>
        <HomeHeader :city="city"></HomeHeader>
        <HomeSwiper :swiperList="swiperList"></HomeSwiper>
        <HomeIcons :iconList="iconList"></HomeIcons>
        <HomeRecommend :recommendList="recommendList"></HomeRecommend>
        <HomeWeekEnd :weekendList="weekendList"></HomeWeekEnd>
    </div>
</template>

<script>
    import  axios from "axios"
    import HomeHeader from "./components/HomeHeader";
    import HomeSwiper from "./components/Swiper";
    import HomeIcons from "./components/Icons";
    import HomeRecommend from "./components/Recommend";
    import HomeWeekEnd from "./components/WeekEnd";
    export default {
        name : "Home",
        components : {
            HomeHeader,
            HomeSwiper,
            HomeIcons,
            HomeRecommend,
            HomeWeekEnd
        },
        data(){
            return {
                city : "",
                swiperList : [],
                iconList : [],
                recommendList : [],
                weekendList : []
            }    
        },
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

    }
</script>

<style lang="stylus" scoped>

    



</style>