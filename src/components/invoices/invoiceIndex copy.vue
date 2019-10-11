<template>
  <div >
    <button @click="invoiceCreate()" class="btn btn-sm btn-dark" >Bir fatura ekle</button>
    <table class="table table-sm">
      <thead>
        <tr>
          <th scope="col">Referans</th>
          <th scope="col">Tarih</th>
          <th scope="col">Firma</th>
          <th scope="col">Kontak</th>
          <th scope="col">Ürün açıklaması</th>
          <th scope="col">Statüs</th>
          <th scope="col">Aksion</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(invoice,index) in invoices" :key="index" >
          <td>{{invoice.referance}}</td>
          <td>{{invoice.date}}</td>
          <td>{{invoice.company.name.slice(0,25)}}</td>
          <td>{{invoice.company.contact.slice(0,20)}}</td>
          <td>{{invoice.mainProduct.slice(0,25)}}</td>
          <td>{{invoice.status}}</td>
          <td>
              <button @click="invoiceShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
              <button @click="invoiceEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
              <button @click="invoiceDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
    methods:{
        invoiceShow: function(index){
            this.$router.push({name:'invoiceView',params: {invoice: this.invoices[index]}})
        },
        invoiceEdit: function(index){
            this.$router.push({name:'invoiceEdit',params: {invoice: this.invoices[index]}})
        },
        invoiceDelete: function(index){
            alert(index)
        },
        invoiceCreate: function(){
            this.$router.push({name:'invoiceCreate',params: {invoice: null} })
        },
       
    },
  data: function() {
    return {
      invoices: [
        {
          id:1,
          type: "Ticari Fatura",
          mainProduct: "250kw 315SM-04 84hz 1029055831",
          date: "26/05/2019",
          referance: "DAL20190101",
          note: "Fatura muhasebe tarafından kesilecektir",
          status: "issued",
          company: {
            name: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
            address:
              "Eyüp Sultan Mahallesi, Eyüpsultan Mah. Müminler Cad. No:70 SANCAKTEPE, 34885 			   SANCAKTEPE/Sancaktepe/İstanbu",
            contact: "Fatih kömürcü"
          },
          items: [ 
            {
              id: 1,
              materialNumber: "1029055831",
              description: "250kw 1029055831 motor bakımı ve rulman değişimi",
              delivery: "4 ay",
              unitPrice: 448,
              qty: 1
            },
            {
              id: 2,
              materialNumber: "bilrsiz",
              description: "Sarım bedeli",
              delivery: "4 ay",
              unitPrice: 617,
              qty: 1
            }
          ]
        },
        {
          id:2,
          type: "Ticari Fatura",
          mainProduct: "250kw 315SM-04 84hz 1029055831",
          date: "27/05/2019",
          referance: "DAL20190101",
          note: "Fatura muhasebe tarafından kesilecektir",
          status: "issued",
          company: {
            name: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
            address:
              "Eyüp Sultan Mahallesi, Eyüpsultan Mah. Müminler Cad. No:70 SANCAKTEPE, 34885 			   SANCAKTEPE/Sancaktepe/İstanbu",
            contact: "Fatih kömürcü"
          },
          items: [
            {
              id: 1,
              materialNumber: "1029055831",
              description: "250kw 1029055831 motor bakımı ve rulman değişimi",
              delivery: "4 ay",
              unitPrice: 448,
              qty: 1
            },
            {
              id: 2,
              materialNumber: "bilrsiz",
              description: "Sarım bedeli",
              delivery: "4 ay",
              unitPrice: 617,
              qty: 1
            }
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>
