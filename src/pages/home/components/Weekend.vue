<template>
    <div>
        <div class="recommend-title">周末推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item in list" :key="item.id">
                <div class="item-image-wrapper">
                    <img class="item-image" :src="item.imgUrl" alt="">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script type="text/ecmascript-6">
export default {
    name: 'HomeWeekend',
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
    line-height 0.8rem
    background #eeeeee
    text-indent 0.2rem
.item-image-wrapper
    height 0
    overflow hidden
    padding-bottom 33.9%
    .item-image
        width 100%
.item-info
    padding 0.1rem
    .item-title
        line-height 0.54rem
        font-size 0.32rem
        ellipisi()
    .item-desc
        line-height 0.4rem
        color #cccccc
        ellipisi()
</style>
