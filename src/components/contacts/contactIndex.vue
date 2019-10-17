<template>
  <div >
      <indexer :data="contacts" :header="header" :nesne="'contact'" ></indexer>
  </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
  name: "contactIndex",
  components:{indexer},
  methods:{},
  data: function() {
    return {
      header: {"companyname":"Firma","name":"İsim","email":"Email","phone":"Telefon"},
      contacts: []
    };
  },
  created: function(){
    axios
    .get('http://localhost:5000/contact')
    .then(res => {
        this.contacts = res.data
        for(var i in this.contacts){
          // console.log(this.contacts[i].company.name)
          this.contacts[i].companyname = this.contacts[i].company.name
        }
        })
    .catch(err => console.log(err))
  },

};
</script>

<style scoped>
</style>
