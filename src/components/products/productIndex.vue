<template>
    <div>
      <indexer :data="products" :header="header" ></indexer>
    </div>
</template>

<script>
import indexer from '../utilities/indexer.vue'
export default {
    name: "productIndex",
    components:{indexer},
    data: function(){
        return {
            header: ["id","ürün kodü","seri numarası","Ürün tipi","Genel bilgi"],
            products: [
                {
                    id: 1,
                    materialNumber: "Material 1",
                    serialNumber: "Serial 1",
                    type: "motor",
                    info: "WEG W22 55kw 1000rpm"
                },    
                {
                    id: 2,
                    materialNumber: "Material 1",
                    serialNumber: "Serial 1",
                    type: "motor",
                    info: "WEG W22 55kw 1000rpm"
                },    
                {
                    id: 3,
                    materialNumber: "Material 1",
                    serialNumber: "Serial 1",
                    type: "motor",
                    info: "WEG W22 55kw 1000rpm"
                },    
                  
            ]
            ,
        };
    },
    methods:{},
    
  

}
</script>

<style>

</style>
