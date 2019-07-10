<template>
  <div id="app">
    <!-- <invoiceView /> -->
    <!-- <invoiceCreate  /> -->
    <!-- <invoiceFrame>    
    <invoiceView />
    </invoiceFrame>     -->
    <invoiceTemplate></invoiceTemplate>
  </div>
</template>

<script>
// import invoiceView from './components/invoiceView.vue'
// import invoiceCreate from './components/invoiceCreate.vue'
// import invoiceFrame from './components/invoiceFrame.vue'
import invoiceTemplate from './components/invoices/invoicetemplate'

export default {
  name: 'app',
  components: {
    // invoiceView,
    // invoiceCreate,
    // invoiceFrame,
    invoiceTemplate
  }
}
</script>

<style>

</style>
