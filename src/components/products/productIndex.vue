<template>
    <div>
      <indexer :data="products" :header="header" :nesne="'product'" ></indexer>
    </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: "productIndex",
    components:{indexer},
    data: function(){
        return {
            header: { "materialNumber" : "ürün kodü", "serialNumber" : "seri numarası","type":"Ürün tipi","info":"Genel bilgi" } ,
            products: []
            ,
        };
    },
    methods:{},
    created: function(){
    axios
    .get('http://localhost:5000/product')
    .then(res => {
        this.products = res.data
        for(var i of this.products){
            if(i.type == 'motor'){
                i.info = i.motor.power + "kW " + i.motor.speed + "RPM"
            }
            else if(i.type == 'vfd'){
                i.info = i.vfd.series + " " + i.vfd.current + "A"
            }
            else if(i.type == 'lsd'){
                i.info = i.lsd.series + " " + i.lsd.motorpower + "kW "
            }
        }
        })
    .catch(err => console.log(err))
  },
    
  

}
</script>

<style>

</style>
