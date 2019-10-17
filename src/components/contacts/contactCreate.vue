<template>
  <div class="container">
    <div class="row justify-content-center">
      <h1>Kontak bilgileri</h1>
    </div>
    <div class="card">
      <div class="card-body">
        <div class="row">
          <hr />
          <div class="col-8">
            <h5>Firma:</h5>
            <p>
              <select class="form-control" v-model="contactcreate.company._id" >
                <option disabled value="0" selected>Firma seçin</option>
                <option v-for="(company,i) in companies" v-bind:key="i" :value="company._id">{{company.name}}</option>
              </select>
            </p>
          </div>
          <div class="col-4">
            <h5>İsim:</h5>
            <p>
              <input
                type="text"
                class="form-control"
                v-model="contactcreate.name"
                placeholder="Süleyman soylu"
              />
            </p>
          </div>
        </div>
        <div class="row">
          <hr />
          <div class="col-8">
            <h5>Email:</h5>
            <p>
              <input
                type="text"
                class="form-control"
                v-model="contactcreate.email"
                placeholder="s.soylu@dalgakıran.com.tr"
              />
            </p>
          </div>
          <div class="col-4">
            <h5>Telefone:</h5>
            <p>
              <input
                type="text"
                class="form-control"
                v-model="contactcreate.phone"
                placeholder="+90 530 306 0000"
              />
            </p>
          </div>
        </div>
      </div>
    </div>

    <br />
    <div class="row justify-content-center">
      <button class="btn btn-success" @click="save()">kaydet</button>
    </div>
    <hr />
  </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios'
export default {
  name: 'contactCreate',
    props: ['contact'],
    data: function () {
      return {
        contactcreate: {
            id: null, 
            name: "", 
            email: "",
            phone: "",
            company: {_id: 0 , name: 'company'},
        },
        companies: [{_id: 0 , name: 'company'}]
      }
    },
    created: function() {
      if (this.contact != null) {
        this.contactcreate = this.contact;
      }
      axios
        .get('http://localhost:5000/company')
        .then(res => {
            this.companies = res.data
            })
        .catch(err => console.log(err))
    },
    methods:{
      save: function (){

          if(this.contact != null){
              this.update()
          }
          else{
              this.create()
          }
      },  
      update: function (){
          axios
          .put('http://localhost:5000/contact',{
            id: this.contactcreate._id, 
            name: this.contactcreate.name, 
            email: this.contactcreate.email,
            phone: this.contactcreate.phone,
            company: this.contactcreate.company._id,
          })
          .then(res => {
              console.log( res.data);
              this.$router.push({name: 'contactIndex'})
              })
          .catch(err => console.log('Update() ' + err))
      },
      create: function(){
          axios
          .post('http://localhost:5000/contact',{
            id: null, 
            name: this.contactcreate.name, 
            email: this.contactcreate.email,
            phone: this.contactcreate.phone,
            company: this.contactcreate.company._id,
          })
          .then(res => {
              console.log( res.data)
              this.$router.push({name: 'contactIndex'})
              })
          .catch(err => console.log('Create() ' + err))
      }  
     
    },

}
</script>

<style scoped>
textarea,
input {
  color: green;
}
</style>
