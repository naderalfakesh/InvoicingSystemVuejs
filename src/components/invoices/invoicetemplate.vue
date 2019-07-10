<template>
  <div class="container py-3 d-flex flex-row">
    <!-- left bar WEG logos component -->
    <leftbar></leftbar>
    <div>
      <!-- Dal Elektrik  header logo and address -->
      <logohead></logohead>
      <hr />
      <!-- Invoice view -->
      <invoiceView :invoiceHeadInfo="invoiceHeadInfo" :itemHeaders="itemHeaders" :items="items"></invoiceView>
      <invoiceCreate :invoiceHeadInfo="{}" :itemHeaders="itemHeaders" :items="[]"></invoiceCreate>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import leftbar from "./leftbar.vue";
import logohead from "./logohead.vue";
import invoiceView from "./invoiceView.vue";
import invoiceCreate from "./invoiceCreate.vue";

export default {
  components: {
    leftbar,
    logohead,
    invoiceView,
    invoiceCreate
  },
  data: function() {
    return {
      invoiceHeadInfo:{
        motorInfo: "250kw 315SM-04 84hz 1029055831",
        date: "27/05/2019",
        referance: "DAL20190101",
        note: "Fatura muhasebe tarafından kesilecektir",
        company: {
          name: "DALGAKIRAN MAKİNE SANAYİ VE TİCARET ANONİM ŞİRKETİ.",
          address:"Eyüp Sultan Mahallesi, Eyüpsultan Mah. Müminler Cad. No:70 SANCAKTEPE, 34885 			   SANCAKTEPE/Sancaktepe/İstanbu",
          contact: "Fatih kömürcü"
        }
      },
      itemHeaders: [
        "#","Ürün kodu","Açıklama","Termin süresi","Birim fiyatı","Miktar","Tutar",
      ],
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
    };
  }
};
</script>

<style scoped>
</style>
