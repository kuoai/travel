<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="list in swiperList" :key="list.id">
                <img 
                    class="swiper-img" 
                    :src="list.imgUrl" 
                    alt=""
                >
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script type="text/ecmascript-6">
export default {
    name: 'HomeSwiper',
    data() {
        return {
            swiperOption: {
                pagination: '.swiper-pagination',
                loop: true
            },
            swiperList: [{
                id: '001',
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/ad906cbe02849a504c4a4399741013a4.jpg_750x200_8ac64dcc.jpg'
            },{
                id: '002',
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/26441ef37316c0d4d081b5fba56873bf.jpg_750x200_910c79ab.jpg'
            }]
        }
    },
}
</script>

<style lang="stylus" scoped>
// 作用域变大
.wrapper >>> .swiper-pagination-bullet-active
    background #ffffff
.wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 26.7%
    background #eeeeee
    
    .swiper-img
        width 100%
</style>
