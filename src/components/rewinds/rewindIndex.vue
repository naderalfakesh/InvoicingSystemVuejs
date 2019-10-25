<template>
    <div>
      <indexer :data="rewinds" :header="header" :nesne="'rewind'" ></indexer>
    </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: "rewindIndex",
    components:{indexer},
    data: function(){
        return{
            header: {"customer":"Müşteri","power":"Güç","pole":"Kutup","voltage":"Gerilim","frequency":"Frekans","serialNumber":"seri numarası","materialNumber":"ürün kodu"},
            rewinds: []
        }
    },
    methods:{},
    created: function(){
        axios
        .get('http://localhost:5000/rewind')
        .then(res => {
            this.rewinds = res.data
            for(let i of this.rewinds){
                i['customer']=i.company.name
                i['power']=i.product.motor.power
                i['pole']=i.product.motor.pole
                i['voltage']=i.product.motor.voltage
                i['frequency']=i.product.motor.frequency
                i['serialNumber']=i.product.serialNumber
                i['materialNumber']=i.product.materialNumber
            }
        })
        .catch(err => console.log(err))
    },
}
</script>

<style>

</style>

