<template>
    <div>
        <div class="search">
            <input type="text" placeholder="输入城市名或拼音" class="search-input" v-model="keyword">
        </div>
        <div class="search-content" v-show="keyword" ref="search">
            <ul>
                <li 
                    class="search-item border-bottom" 
                    v-for="item in list"
                    :key="item.id"
                >
                    {{item.name}}</li>
                <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
            </ul>
        </div>
    </div>
</template>

<script type="text/ecmascript-6">
import Bscroll from 'better-scroll'
export default {
    name: 'CitySearch',
    props: {
        cities: Object
    },
    data() {
        return {
            keyword: '',
            list: [],
            timer: null,

        }
    },
    computed: {
        hasNoData(){
            return !this.list.length
        }
    },
    watch: {
        keyword(){
            if(this.timer){
                clearTimeout(this.timer)
            }
            if(!this.keyword){
                this.list = []
                return
            }
            this.timer = setTimeout(()=>{
                const result = []
                for(let i in this.cities){
                    this.cities[i].forEach((value)=>{
                        if(value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1){
                            result.push(value)
                        }
                    })
                }
                this.list = result
            },100)
        }
    },
    mounted() {
        this.scroll = new Bscroll(this.$refs.search)
    },
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.search
    height 0.72rem
    background-color $bgColor
    padding 0 0.1rem
    .search-input
        box-sizing border-box
        height 0.62rem
        line-height 0.62rem
        width 100%
        padding 0 0.1rem
        text-align center
        border-radius 0.06rem
        color #666
.search-content
    overflow hidden
    z-index 1
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    background-color #eeeeee 
    .search-item
        line-height 0.62rem
        padding-left 0.2rem
        color #666
        background-color #ffffff

</style>
