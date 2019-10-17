<template>
    <div>
        <div class="card">
            <div class="card-body">
                <div class="row">
                    <div class="col">
                        <h5>İsim</h5>
                        <p><input v-model="companyCreate.name" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Tip</h5>
                        <p><input v-model="companyCreate.type" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Email</h5>
                        <p><input v-model="companyCreate.email" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Website</h5>
                        <p><input v-model="companyCreate.website" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Telefon</h5>
                        <p><input v-model="companyCreate.phone" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Fax</h5>
                        <p><input v-model="companyCreate.fax" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Vergi dairesi</h5>
                        <p><input v-model="companyCreate.taxAdmin" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Vergi Numarası</h5>
                        <p><input v-model="companyCreate.taxNumber" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Adres</h5>
                        <div class="form-inline">
                            <div class="form-group"  v-for="(adres,i) in companyCreate.addresses" v-bind:key="i">
                                <!-- <input v-model="adres.main" type="checkbox" class="form-control"> -->
                                <input v-model="adres.address" type="text" class="form-control">
                            </div>
                        </div>

                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <button @click="save()" class="btn btn-primary">Kaydet</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
 /* eslint-disable */
import axios from 'axios'
export default {
    name: 'companyCreate',
    props: ['company'],
    data: function(){
        return{
            companyCreate:{
                id: null,
                name: "",
                type: "",
                email: "",
                website: "",
                phone: "",
                fax: "",
                taxAdmin:"",
                taxNumber:"",
                addresses: [{main: true , address: ""}] ,
            }
        };
    },
    created: function(){
        if(this.company != null){
            this.companyCreate = this.company
        }
    },
    methods:{
      save: function (){
          if(this.company != null){
              this.update()
          }
          else{
              this.create()
          }
      },  
      update: function (){
          axios
          .put('http://localhost:5000/company',{
            id: this.companyCreate._id,
            name: this.companyCreate.name,
            type: this.companyCreate.type,
            email: this.companyCreate.email,
            website: this.companyCreate.website,
            phone: this.companyCreate.phone,
            fax: this.companyCreate.fax,
            taxAdmin: this.companyCreate.taxAdmin,
            taxNumber: this.companyCreate.taxNumber,
            addresses: this.companyCreate.addresses
          })
          .then(res => {
              console.log( res.data);
              this.$router.push({name: 'companyIndex'})
              })
          .catch(err => console.log(err))
      },
      create: function(){
          axios
          .post('http://localhost:5000/company',{
            id: null,
            name: this.companyCreate.name,
            type: this.companyCreate.type,
            email: this.companyCreate.email,
            website: this.companyCreate.website,
            phone: this.companyCreate.phone,
            fax: this.companyCreate.fax,
            taxAdmin: this.companyCreate.taxAdmin,
            taxNumber: this.companyCreate.taxNumber,
            addresses: this.companyCreate.addresses
          })
          .then(res => {
              console.log( res.data);
              this.$router.push({name: 'companyIndex'})
              })
          .catch(err => console.log(err))
      }  
    },
}
</script>

<style>

</style>
