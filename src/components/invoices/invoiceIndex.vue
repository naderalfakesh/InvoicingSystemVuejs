<template>
  <div>
    <indexer :data="invoices" :header="header" :nesne="'invoice'" ></indexer>
  </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: 'invoiceIndex',
    components:{indexer},
    methods:{},
  data: function() {
    return {
      header: {"referance":"Referans", "date":"Tarih","companyname":"Firma","contactname":"Kontak","productsummary":"Ürün açıklaması","status":"Statüs"},
      invoices: []
    };
  },
  created: function(){
    axios
    .get('http://localhost:5000/invoice')
    .then(res => {
        this.invoices = res.data
        for(var i in this.invoices){
          this.invoices[i].companyname = this.invoices[i].company.name
          this.invoices[i].contactname = this.invoices[i].contact.name
          this.invoices[i].productsummary = this.invoices[i].product.summary
        }
        })
    .catch(err => console.log(err))
  },

};
</script>

<style scoped>
</style>
