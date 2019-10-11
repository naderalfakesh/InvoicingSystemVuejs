<template>
  <div >
    <button @click="contactCreate()" class="btn btn-sm btn-dark" >Bir kontak ekle</button>
    <table class="table table-sm">
      <thead>
        <tr>
          <th>#</th>
          <th>Firma</th>
          <th>İsim</th>
          <th>Email</th>
          <th>Telefon</th>
          <th>Aksyon</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(contact,index) in contacts" :key="index" >
          <td>{{index+1}}</td>
          <td>{{contact.company}}</td>
          <td>{{contact.name}}</td>
          <td>{{contact.email}}</td>
          <td>{{contact.phone}}</td>
          <td>
              <button @click="contactShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
              <button @click="contactEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
              <button @click="contactDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
    methods:{
        contactShow: function(index){
            this.$router.push({name:'contactView',params: {contact: this.contacts[index]}})
        },
        contactEdit: function(index){
            this.$router.push({name:'contactEdit',params: {contact: this.contacts[index]}})
        },
        contactDelete: function(index){
            alert(index)
            this.contacts.splice(index,1)
        },
        contactCreate: function(){
            this.$router.push({name:'contactCreate',params: {contact: null} })
        },
       
    },
  data: function() {
    return {
      contacts: [
        {
          company:"company number 1",
          name:"name number 1",
          email:"email number 1",
          phone:"phone number 1" 
        },
        {
          company:"company number 2",
          name:"name number 2",
          email:"email number 2",
          phone:"phone number 2" 
        },
        {
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
