<template>
   <div class="header">
       <div class="header-left">
           <div class="iconfont back-icon">&#xe624;</div>
       </div>
       <div class="header-input">
           <span class="iconfont">&#xe632;</span>
           输入城市/景点/游玩主题
       </div>
       <div class="header-right">
           城市
           <span class="iconfont">&#xe6aa;</span>
       </div>
   </div>
</template>

<script type="text/ecmascript-6">
export default {
    name: 'HomeHeader',
    data() {
        return {
        }
    },
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
// 1rem = html font-size = 50px
// 86/100 = 0.86rem
.header
    line-height 0.86rem
    display flex
    background $bgColor
    color #fff
    .header-left
        width 0.64rem
        float left
        .back-icon
            text-align center
            font-size 0.35rem
    .header-input
        flex 1
        line-height 0.64rem
        height 0.64rem
        margin-top 0.12rem
        margin-left 0.2rem
        padding-left 0.2rem
        background #ffffff
        border-radius 0.1rem
        color #cccccc
    .header-right
        width 1.24rem
        float right
        text-align center
</style>
