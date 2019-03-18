<template>
   <div class="icons">
       <swiper>
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
    data() {
        return {
            iconlist:[{
                id: '0001',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                desc: '景点门票'
            },{
                id: '0002',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                desc: '一日游'
            },{
                id: '0003',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
                desc: '自然风光'
            },{
                id: '0004',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
                desc: '海洋馆'
            },{
                id: '0005',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                desc: '大连必游'
            },{
                id: '0006',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
                desc: '泡温泉'
            },{
                id: '0007',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
                desc: '亲子游'
            },{
                id: '0008',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/90/59a2f523ee2f9202.png',
                desc: '农家度假'
            },{
                id: '0009',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
                desc: '展馆展览'
            }]
        }
    },
    computed: {
        pages(){
            const pages = []
            this.iconlist.forEach((item, index)=>{
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
