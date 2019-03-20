<template>
    <div>
        <city-header></city-header>
        <city-search :cities="cities"></city-search>
        <city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
        <city-alphabet @change="handleLetterChange" :cities="cities"></city-alphabet>
    </div>
</template>

<script type="text/ecmascript-6">
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
    name: 'City',
    data() {
        return {
            cities: {},
            hotCities: [],
            letter: ''
        }
    },
    components: {
        CityHeader,
        CitySearch,
        CityList,
        CityAlphabet
    },
    methods: {
        geyCityInfo(){
            axios.get("/api/city.json")
            .then(this.handleGetCityInfoSucc)
        },
        handleGetCityInfoSucc(res){
            res = res.data
            if(res.ret && res.data){
                const data = res.data
                this.cities = data.cities
                this.hotCities = data.hotCities
            }
        },
        // 父组件接受子组件传来的参数
        handleLetterChange(letter){
            this.letter = letter;
        }
    },
    mounted() {
        this.geyCityInfo()
    },
}
</script>

<style lang="stylus" scoped>
</style>
