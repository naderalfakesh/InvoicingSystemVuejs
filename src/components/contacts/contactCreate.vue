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
              <input
                type="text"
                class="form-control"
                v-model="contactcreate.company"
                placeholder="Dalgakıran A.Ş."
              />
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
                placeholder="Süleyman soylu"
              />
            </p>
          </div>
        </div>
      </div>
    </div>

    <br />
    <div class="row justify-content-center">
      <button class="btn btn-success" @click="createContact()">kontak kaydet</button>
    </div>
    <hr />
  </div>
</template>

<script>
export default {
    props: ['contact'],
    data: function () {
      return {
        contactcreate: {
            id: null, 
            company: "",
            name: "", 
            email: "",
            phone: "",
        }
      }
    },
    methods:{
        createContact:function(){
            alert("Saving function goes here")
        }
    },
    created: function() {
    if (this.contact != null) {
      this.contactcreate = this.contact;
    }
    }

}
</script>

<style scoped>
textarea,
input {
  color: green;
}
</style>
