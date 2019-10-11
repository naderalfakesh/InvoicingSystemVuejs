<template>
<div>
    <indexer :data="lsds" :header="header" ></indexer>
</div>
</template>

<script>
import indexer from '../utilities/indexer.vue'
export default {
    name: "lsdCreate",
    components:{indexer},
    data: function(){
        return {
            header: ["id","Sipariş tarihi","Müşteri","Model","Motor markası","İstenen tarihi","Statüs"],
            lsds:[
                {
                id: 1,
                orderDate: "02-01-1991", 
                company: "Ersel Ağır makia san. tic. aş.",
                model: "LSDEmini 19010",
                motorBrand: "ABB",
                wantedDeliveryDate: "02-02-1991", 
                status: "Teslim edilmiştir",
                },
                {
                id: 2,
                orderDate: "02-01-1991", 
                company: "Ersel",
                model: "LSDEmini 19011",
                motorBrand: "ABB",
                wantedDeliveryDate: "02-02-1991", 
                status: "Teslim edilmiştir",
                },
                {
                id: 3,
                orderDate: "02-01-1991", 
                company: "Ersel",
                model: "LSDEmini 19012",
                motorBrand: "ABB",
                wantedDeliveryDate: "02-02-1991", 
                status: "Teslim edilmiştir",
                },
        ],

        };
    },
    methods:{},

}
</script>

<style>

</style>
