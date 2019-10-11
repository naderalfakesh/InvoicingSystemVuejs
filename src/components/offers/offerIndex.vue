<template>
    <div>
      <indexer :data="offers" :header="header" ></indexer>
    </div>
</template>

<script>
import indexer from '../utilities/indexer.vue'
export default {
    name: "offerIndex",
    components:{indexer},
    data: function(){
        return {
            header: ["id","Referans","Tarih","Firma","Kontak","Ürün açıklaması","Statüs"],
            offers:[
                {
                    id: 1,
                    referance: "DAL20190101",
                    date: "26/05/2019",
                    companyName: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
                    companyContact: "Fatih kömürcü",
                    mainProduct: "250kw 315SM-04 84hz 1029055831",
                    status: "issued"
                },
                {
                    id: 2,
                    referance: "DAL20190101",
                    date: "26/05/2019",
                    companyName: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
                    companyContact: "Fatih kömürcü",
                    mainProduct: "250kw 315SM-04 84hz 1029055831",
                    status: "issued"
                },
                {
                    id: 3,
                    referance: "DAL20190101",
                    date: "26/05/2019",
                    companyName: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
                    companyContact: "Fatih kömürcü",
                    mainProduct: "250kw 315SM-04 84hz 1029055831",
                    status: "issued"
                },
            ]
        };
    },
    methods:{},
}
</script>

<style>

</style>
