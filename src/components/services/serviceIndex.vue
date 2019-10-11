<template>
  <div >
      <indexer :data="services" :header="header" ></indexer>
  </div>
</template>

<script>
import indexer from '../utilities/indexer.vue'
export default {
    name: "serviceIndex",
    components:{indexer},
    methods:{},
  data: function() {
    return {
      header: ["id","Firma","İsim","Email","Telefon"],
      services: [
        {
          id: 1,
          company:"company number 1",
          name:"name number 1",
          email:"email number 1",
          phone:"phone number 1" 
        },
        {
          id:2,
          company:"company number 2",
          name:"name number 2",
          email:"email number 2",
          phone:"phone number 2" 
        },
        {
          id:3,
          company:"company number 3",
          name:"name number 3",
          email:"email number 3",
          phone:"phone number 3" 
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>
