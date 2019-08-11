<template>
    <div>
        <div class="card border-primary my-3">
            <div class="card-header text-primary">
                <h5>Teklifler</h5>
            </div>
            <div class="card-body">
                <table class="table table-sm">
                    <thead class="table-primary">
                        <th scope="col">Referans</th>
                        <th scope="col">Tarih</th>
                        <th scope="col">Firma</th>
                        <th scope="col">Kontak</th>
                        <th scope="col">Ürün açıklaması</th>
                        <th scope="col">Statüs</th>
                        <th scope="col">Aksion</th>
                    </thead>
                    <tbody>
                        <tr v-for="(offer,index) in offers" :key="index" >
                            <td>{{offer.referance}}</td>
                            <td>{{offer.date}}</td>
                            <td>{{offer.company.name.slice(0,25)}}</td>
                            <td>{{offer.company.contact.slice(0,20)}}</td>
                            <td>{{offer.mainProduct.slice(0,25)}}</td>
                            <td>{{offer.status}}</td>
                            <td>
                                <button @click="offerShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                                <button @click="offerEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                                <button @click="offerDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "offerIndex",
    data: function(){
        return {
            offers:[
                {
                    id: 1,
                    mainProduct: "250kw 315SM-04 84hz 1029055831",
                    date: "26/05/2019",
                    referance: "DAL20190101",
                    note: "Fatura muhasebe tarafından kesilecektir",
                    status: "issued",
                    company: {
                        name: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
                        address:
                        "Eyüp Sultan Mahallesi, Eyüpsultan Mah. Müminler Cad. No:70 SANCAKTEPE, 34885 			   SANCAKTEPE/Sancaktepe/İstanbu",
                        contact: "Fatih kömürcü"
                    },
                    items: [
                        {
                        id: 1,
                        materialNumber: "1029055831",
                        description: "250kw 1029055831 motor bakımı ve rulman değişimi",
                        delivery: "4 ay",
                        unitPrice: 448,
                        qty: 1
                        },
                        {
                        id: 2,
                        materialNumber: "bilrsiz",
                        description: "Sarım bedeli",
                        delivery: "4 ay",
                        unitPrice: 617,
                        qty: 1
                        }
                    ]
                },
              
            ]
        };
    },
    methods:{
        offerShow: function(index){
            this.$router.push({name:'offerView',params: {offer: this.offers[index]}})
        },
        offerEdit: function(index){
            this.$router.push({name:'offerEdit',params: {offer: this.offers[index]}})
        },
        offerDelete: function(index){
            alert(index)
        },
        offerCreate: function(){
            this.$router.push({name:'offerCreate',params: {offer: null} })
        },
    },
}
</script>

<style>

</style>
