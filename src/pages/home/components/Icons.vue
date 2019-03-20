<template>
   <div class="icons">
       <swiper :options="swiperOption">
            <swiper-slide v-for="(page, index) in pages" :key="index">
                <div class="icon" v-for="item in page" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src='item.imgUrl' alt="">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
       </swiper>
   </div>
</template>

<script type="text/ecmascript-6">
export default {
    name: 'HomeIcons',
    props: {
        list: Array
    },
    data() {
        return {
            swiperOption: {
                autoplay: false
            }
        }
    },
    computed: {
        pages(){
            const pages = []
            this.list.forEach((item, index)=>{
                const page = Math.floor(index/8)
                if(!pages[page]){
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages;
        }
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';
.icons >>> .swiper-container
    height 0
    padding-bottom 50%
.icons
    margin-top 0.1rem
    .icon
        width 25%
        height 0
        float left
        padding-bottom 25%
        overflow hidden
        position relative
        .icon-img
            position absolute
            top 0px
            left 0px
            right 0px
            bottom 0.44rem
            box-sizing border-box
            padding 0.03rem
            .icon-img-content
                height 100%
                display block
                margin 0 auto
        .icon-desc
            position absolute
            left 0
            right 0
            bottom 0
            line-height 0.44rem
            height 0.44rem
            text-align center
            color $darkTextColor
            ellipisi()
</style>
