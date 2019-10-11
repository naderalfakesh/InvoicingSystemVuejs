<template>
  <div>
      <indexer :data="companies" :header="header" ></indexer>
  </div>
</template>

<script>
import indexer from '../utilities/indexer.vue'
export default {
    components:{indexer},
    data: function(){
        return {
            header: ["id","name","type","email","website","phone","fax","taxAdmin","taxNumber","address"],
            companies:[
                {
                    id: 1,
                    name: "name 1",
                    type: "type 1",
                    email: "email 1",
                    website: "website 1",
                    phone: "phone 1",
                    fax: "fax 1",
                    taxAdmin:"tax admin 1",
                    taxNumber:"tax number 1",
                    address:"address 1",
                },
                {
                    id: 2,
                    name: "name 2",
                    type: "type 2",
                    email: "email 2",
                    website: "website 2",
                    phone: "phone 2",
                    fax: "fax 2",
                    taxAdmin:"tax admin 2",
                    taxNumber:"tax number 2",
                    address:"address 2",
                },
                {
                    id: 3,
                    name: "name 3",
                    type: "type 3",
                    email: "email 3",
                    website: "website 3",
                    phone: "phone 3",
                    fax: "fax 3",
                    taxAdmin:"tax admin 3",
                    taxNumber:"tax number 3",
                    address:"address 3",
                }
            ]
        };
    },

}
</script>

<style>

</style>