<template>

    <div class="container">
      <div class="row justify-content-center">
        <h1>{{invoiceHeadInfo.type}}</h1>
      </div>
      <div class="card">
        <div class="card-body">
          <div class="row">
            <hr />
            <div class="col-8">
              <h5>Motor bilgileri:</h5>
              <p>
                <input
                  type="text"
                  class="form-control"
                  v-model="invoiceHeadInfo.motorInfo"
                  placeholder="30kw 02p W22 B35"
                />
              </p>
            </div>
            <div class="col-4">
              <h5>Tarih:</h5>
              <p>
                <input type="text" class="form-control" v-model="invoiceHeadInfo.date" placeholder="01/01/2019" />
              </p>
            </div>
        </div>

        <div class="row">
          <div class="col-8">
            <h5>Firma unvanı:</h5>
            <p>
              <input
                type="text"
                class="form-control"
                v-model="invoiceHeadInfo.company.name"
                placeholder="Dal Elektrik A.Ş."
              />
            </p>
          </div>
          <div class="col-4">
            <h5>Referans :</h5>
            <p>
              <input type="text" class="form-control" v-model="invoiceHeadInfo.referance" placeholder="Dal20190101" />
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-8">
            <h5>Adres :</h5>
            <p>
              <input
                type="text"
                class="form-control"
                v-model="invoiceHeadInfo.company.address"
                placeholder="Adnan Kahveci Bulvarı, Haydar Akın İş Merkezi-1 No:206 Kat:4. 34188 Şirinevler-İstanbul Tel:0212 451 56 06 www.dal.com.tr"
              />
            </p>
          </div>
          <div class="col-4">
            <h5>kontak kişi :</h5>
            <p>
              <input
                type="text"
                class="form-control"
                v-model="invoiceHeadInfo.company.contact"
                placeholder="Nadir bey"
              />
            </p>
          </div>
        </div>
      </div>
      </div>
      <br>

      <div class="row">
        <table class="table table-sm" id="invoiceTable">
          <thead>
            <tr>
              <th v-for="(itemHeader,index) in itemHeaders" :key="index" scope="col">{{itemHeader}}</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(item, index ) in items" v-bind:key="index">
              <th scope="row"><button v-if="index>0" type="button" class="btn btn-sm btn-danger" @click="deleteRow(index)" >X</button></th>
              <td><input v-model="item.materialNumber" type="text"  class="form-control"  placeholder="0123456789" ></td>
              <td><input v-model="item.description" type="text"  class="form-control"   placeholder="4kw 0p W22 motor"></td>
              <td><input v-model="item.delivery" type="text"  class="form-control"   placeholder="4 ay"></td>
              <td><input v-model="item.unitPrice" type="text"  class="form-control"   placeholder="0"></td>
              <td><input v-model="item.qty" type="text"  class="form-control"   placeholder="0"></td>
              <td>{{item.unitPrice*item.qty}}</td>
            </tr>
            
            <tr class="table-success">
              <td ><button class="btn btn-sm btn-primary" type="button" @click="addrow()">+</button></td>
              <td colspan="3">
                <strong class="d-flex justify-content-center">Toplam</strong>
              </td>
              <td colspan="3">
                <strong class="d-flex justify-content-center">
                  <u>{{total()}} Euro + KDV</u>
                </strong>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="row ">
        <h5>Notes</h5>
        <textarea v-model="invoiceHeadInfo.note" class="form-control" cols="20" rows="3"></textarea>
      </div>
      <br>
      <div class="row justify-content-center">
        <button class="btn btn-success" @click="createInvoice()">Fatura kaydet</button>
      </div>
      <hr />
      <div class="row">
        <h6>Yetkili :</h6>
        <pre class="text-uppercase"> Nader Alfakesh / Servis müh / nader.alfakesh@dal-group.com</pre>
      </div>
    </div>
  
</template>

<script>


export default {
  name: "invoiceCreate",
  props: {
  //  invoiceHeadInfo : Object,
  //  items : Array,
   itemHeaders : Array
  },
  components: {
   
  },
  methods: {
    total: function() {
      let tmp = 0;
      this.items.forEach(fofo);
      function fofo(item) {
        tmp += item.qty * item.unitPrice;
      }
      return tmp;
    },
    addrow: function(){
      this.items.push( {
          id: "",
          materialNumber: "",
          description: "",
          unitPrice: "",
          qty: ""
        })

    },
    deleteRow: function(index){
      this.items.splice(index,1)
    },
    createInvoice: function(){
      alert("Here we save the data with fetch API")
      
    }

  },
  data: function() {
    return {
      invoiceHeadInfo:{
        type:"nader",
        motorInfo: "",
        date: "",
        referance: "",
        note: "Fatura muhasebe tarafından kesilecektir",
        company: {
          name: "",
          address:"",
          contact: ""
        }
      },
      items: [
        {
          id: "",
          materialNumber: "",
          description: "",
          delivery: "",
          unitPrice: "",
          qty: ""
        }
      ],

      
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dallogo {
  height: 50px;
  width: auto;
}
.weglogo {
  height: 50px;
  width: auto;
}
textarea,input {
  color: green;
}

</style>
