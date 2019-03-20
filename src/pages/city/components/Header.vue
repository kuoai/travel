<template>
   <div class="header">
       城市选择
       <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>
       </router-link>
   </div>
</template>

<script type="text/ecmascript-6">
export default {
    name: 'CityHeader',
    data() {
        return {
        }
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
    height 0.86rem
    line-height 0.86rem
    overflow hidden
    text-align center
    color #ffffff
    background-color $bgColor
    font-size 0.32rem
    position relative
    .header-back
        width 0.64rem
        text-align center
        font-size 0.4rem
        position absolute
        top 0
        left 0
        color #ffffff
</style>
