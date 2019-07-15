<script>
import invoiceIndex from "./components/invoices/invoiceIndex";
import invoiceView from "./components/invoices/invoiceView";
import invoiceCreate from "./components/invoices/invoiceCreate";
import contactIndex from "./components/contacts/contactIndex";
import contactView from "./components/contacts/contactView";
import contactCreate from "./components/contacts/contactCreate";
import companyIndex from "./components/companies/companyIndex";
import companyView from "./components/companies/companyView";
import companyCreate from "./components/companies/companyCreate";

export default [
  {
    path: "/",
    name: "homePage",
    component: null,
    props: false
    
  },
  {
    path: "/invoices",
    name: "invoiceIndex",
    components: {default: invoiceIndex, invoice: invoiceIndex},
    props: false
  },
  {
    path: "/invoice/view",
    name: "invoiceView",
    component: invoiceView,
    props: true
  },
  {
    path: "/invoice/create",
    name: "invoiceCreate",
    component: invoiceCreate,
    props: true
  },
  {
    path: "/invoice/edit",
    name: "invoiceEdit",
    component: invoiceCreate,
    props: true
  },
  {
    path: "/contacts",
    name: "contactIndex",
    component: contactIndex,
    props: false
  },
  {
    path: "/contact/view",
    name: "contactView",
    component: contactView,
    props: true
  },
  {
    path: "/contact/create",
    name: "contactCreate",
    component: contactCreate,
    props: true
  },
  {
    path: "/contact/edit",
    name: "contactEdit",
    component: contactCreate,
    props: true
  },
  {
    path: "/companies",
    name: "companyIndex",
    component: companyIndex,
    props: false
  },
  {
    path: "/company/view",
    name: "companyView",
    component: companyView,
    props: true
  },
  {
    path: "/company/edit",
    name: "companyEdit",
    component: companyCreate,
    props: true
  },
  {
    path: "/company/create",
    name: "companyCreate",
    component: companyCreate,
    props: true
  },
];
</script>



