<template>
    <div>
      <indexer :data="nameplates" :header="header" :nesne="'nameplate'" ></indexer>
    </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: "nameplateIndex",
    components:{indexer},
    data: function(){
        return {
            header: {"materialNumber":"Ürün kodu","model":"model","powers":"Güç","frame":"Gövde","pole":"kutup sayısı","serialNumber":"Seri numarası"},
            nameplates:[]
        };
    },
    created: function(){
        axios
        .get('http://localhost:5000/nameplate')
        .then(res => {
            this.nameplates = res.data
            for(let nameplate of this.nameplates){
                nameplate['powers']=nameplate.power[0]+"kW"
            }
            })
        .catch(err => console.log(err))
    },
    methods:{},
}
</script>

<style>

</style>
