<template>
    <div>
      <indexer :data="nameplates" :header="header" :nesne="'nameplate'" ></indexer>
    </div>
</template>

<script>
import indexer from '../utilities/indexer.vue'
export default {
    name: "nameplateIndex",
    components:{indexer},
    data: function(){
        return {
            header: ["id","Ürün kodu","model","Güç","Gövde","kutup sayısı","Seri numarası"],
            nameplates:[
                {
                    id: 1,
                    materialNumber: "14888427",
                    model:"W22",
                    voltage: "400V",
                    frame: "250S/M",
                    pole: "04P",
                    serialNumber: "1049107714",
                },
                {
                    id: 2,
                    materialNumber: "14888427",
                    model:"W22",
                    voltage: "400V",
                    frame: "250S/M",
                    pole: "04P",
                    serialNumber: "1049107714",
                },
                {
                    id: 3,
                    materialNumber: "14888427",
                    model:"W22",
                    voltage: "400V",
                    frame: "250S/M",
                    pole: "04P",
                    serialNumber: "1049107714",
                },
            ]
        };
    },
    methods:{},
}
</script>

<style>

</style>
