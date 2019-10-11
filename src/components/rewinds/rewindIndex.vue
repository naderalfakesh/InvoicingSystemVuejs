<template>
    <div>
      <indexer :data="rewinds" :header="header" ></indexer>
    </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
export default {
    name: "rewindIndex",
    components:{indexer},
    data: function(){
        return{
            header: ["id","Müşteri","Güç","Kutup","Gerilim","Frekans","seri numarası","ürün kodu"],
            rewinds: [
                {
                    id: 1,
                    customer: "Dalgakıran",
                    power: "55kw",
                    pole:  "06P",
                    voltage: "400V",
                    frequency: "50Hz",
                    serialNumber: "0987654321",
                    materialNumber: "1234567890",
                },
                {
                    id: 2,
                    customer: "Dalgakıran",
                    power: "55kw",
                    pole:  "06P",
                    voltage: "400V",
                    frequency: "50Hz",
                    serialNumber: "0987654321",
                    materialNumber: "1234567890",
                },
                {
                    id: 3,
                    customer: "Dalgakıran",
                    power: "55kw",
                    pole:  "06P",
                    voltage: "400V",
                    frequency: "50Hz",
                    serialNumber: "0987654321",
                    materialNumber: "1234567890",
                }
            ]
        }
    },
    methods:{},
    mounted: function () {
        console.log('nader')
        fetch("https://f6c6bf7e-5f22-4ba3-b781-8bc7cf823b21.mock.pstmn.io/companies").then((resp) => resp.json()) // Transform the data into json
         .then(function(data) {
            console.log(data)
            })
            
    }
}
</script>

<style>

</style>

