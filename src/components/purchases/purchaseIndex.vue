<template>
  <div>
    <indexer :data="purchases" :header="header" :nesne="'purchase'" ></indexer>
  </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: 'purchaseIndex',
    components:{indexer},
    methods:{},
  data: function() {
    return {
      header: {"referance":"Referans", "date":"Tarih","companyname":"Firma","contactname":"Kontak","productsummary":"Ürün açıklaması","status":"Statüs"},
      purchases: []
    };
  },
  created: function(){
    axios
    .get('http://localhost:5000/invoice/purchase')
    .then(res => {
        this.purchases = res.data
        for(var i in this.purchases){
          this.purchases[i].companyname = this.purchases[i].company.name
          this.purchases[i].contactname = this.purchases[i].contact.name
          this.purchases[i].productsummary = this.purchases[i].product.summary
        }
        })
    .catch(err => console.log(err))
  },

};
</script>

<style scoped>
</style>
