<template>
  <div>
    <indexer :data="offers" :header="header" :nesne="'offer'" ></indexer>
  </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: 'offerIndex',
    components:{indexer},
    methods:{},
  data: function() {
    return {
      header: {"referance":"Referans", "date":"Tarih","companyname":"Firma","contactname":"Kontak","productsummary":"Ürün açıklaması","status":"Statüs"},
      offers: []
    };
  },
  created: function(){
    axios
    .get('http://localhost:5000/invoice/offer')
    .then(res => {
        this.offers = res.data
        for(var i in this.offers){
          this.offers[i].companyname = this.offers[i].company.name
          this.offers[i].contactname = this.offers[i].contact.name
          this.offers[i].productsummary = this.offers[i].product.summary
        }
        })
    .catch(err => console.log(err))
  },

};
</script>

<style scoped>
</style>
