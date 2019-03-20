<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item in list" :key="item.id">
                <img height="80" width="80" class="item-image" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script type="text/ecmascript-6">
export default {
    name: 'HomeRecommend',
    props: {
        list: Array
    },
    data() {
        return {
            
        }
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend-title
    margin-top 0.2rem
    line-height 0.8rem
    background #eeeeee
    text-indent 0.2rem
.item
    display flex 
    height 1.8rem
    overflow hidden
    .item-image
        padding 0.1rem
    .item-info
        flex 1
        padding 0.1rem
        min-width 0
        .item-title
            line-height 0.54rem
            font-size 0.32rem
            ellipisi()
        .item-desc
            line-height 0.4rem
            color #cccccc
            ellipisi()
        .item-button
            background-color #ff9300
            padding 0 0.2rem
            line-height 0.44rem
            border-radius 0.06rem
            margin-top 0.2rem
            color #ffffff

</style>
