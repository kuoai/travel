<template>
   <div class="list" ref="wrapper">
       <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div 
                        class="button-wrapper"
                        v-for="item in hot"
                        :key="item.id"
                    >
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item, key) in cities" :key="key" :ref="key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div 
                        class="item border-bottom"
                        v-for="innerItem in item"
                        :key="innerItem.id"
                    >
                        {{innerItem.name}}
                    </div>
                </div>
            </div>
        </div>
   </div>
</template>

<script type="text/ecmascript-6">
import Bscroll from 'better-scroll';
export default {
    name: 'CityList',
    props:{
        hot: Array,
        cities: Object,
        letter: String
    },
    data() {
        return {
        }
    },
    mounted() {
        this.scroll = new Bscroll(this.$refs.wrapper)
    },
    // 监听器
    watch: {
        letter(){
            if(this.letter){
                const element = this.$refs[this.letter][0]
                this.scroll.scrollToElement(element)
            }
        }
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.border-topbottom
    &:before
        border-color #ccc
    &:after
        border-color #ccc
.border-bottom
    &:before
        border-color #ccc
.list
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    .title
        line-height 0.54rem
        background-color #eeeeee
        padding-left 0.2rem
        font-size 0.26rem
        color #666
    .button-list
        padding 0.1rem
        overflow hidden
        padding 0.1rem 0.6rem 0.1rem 0.1rem
        .button-wrapper
            width 33.3%
            float left
            .button
                padding 0.1rem
                text-align center
                margin 0.1rem
                border 0.02rem solid #cccccc
                border-radius 0.06rem
    .item-list
        .item
            line-height 0.72rem
            color #666
            padding-left 0.2rem
</style>
