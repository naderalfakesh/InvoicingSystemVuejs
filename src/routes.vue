<script>
import invoiceIndex from "./components/invoices/invoiceIndex";

export default [
  {
    path: "/",
    name: "homePage",
    
  },
  {
    path: "/invoices",
    name: "invoiceIndex",
    component: invoiceIndex,
    props: false
  }
];
</script>



