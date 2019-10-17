<template>
    <div>
         <indexer :data="companies" :header="header" :nesne="'company'"></indexer>
    </div>
</template>

<script>
/* eslint-disable */
import indexer from '../utilities/indexer.vue'
import axios from 'axios'
export default {
    name: 'companyIndex',
    components:{indexer},
    data: function(){
        return {
            header: {"name":"Firma","type":"tip","email":"Eposta","website":"Websitesi","phone":"Tel","fax":"Fax"},
            companies:[]
        };
    },
    created: function(){
        axios
        .get('http://localhost:5000/company')
        .then(res => {
            this.companies = res.data
            })
        .catch(err => console.log(err))
    },
    methods:{} 
}
</script>

<style>

</style>
