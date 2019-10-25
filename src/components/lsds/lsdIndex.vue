<template>
<div>
    <indexer :data="lsds" :header="header" :nesne="'lsd'" ></indexer>
</div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: "lsdIndex",
    components:{indexer},
    data: function(){
        return {
            header: {"orderDate":"Sipariş tarihi","customer":"Müşteri","model":"Model","motorBrand":"Motor markası","wantedDeliveryDate":"İstenen tarihi","status":"Statüs"},
            lsds:[],

        };
    },
    created: function(){
        axios
        .get('http://localhost:5000/lsd')
        .then(res => {
            this.lsds = res.data
            for(let lsd of this.lsds){
                lsd['customer']=lsd.company.name
                lsd['motorBrand']=lsd.motorInfo.brand
            }
            })
        .catch(err => console.log(err))
    },
    methods:{},

}
</script>

<style>

</style>
