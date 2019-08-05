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
import productIndex from "./components/products/productIndex";
import productView from "./components/products/productView";
import productCreate from "./components/products/productCreate";
import rewindIndex from "./components/rewinds/rewindIndex";
import rewindView from "./components/rewinds/rewindView";
import rewindCreate from "./components/rewinds/rewindCreate";
import lsdIndex from "./components/lsds/lsdIndex";
import lsdView from "./components/lsds/lsdView";
import lsdCreate from "./components/lsds/lsdCreate";

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
  {
    path: "/products",
    name: "productIndex",
    component: productIndex,
    props: false
  },
  {
    path: "/product/view",
    name: "productView",
    component: productView,
    props: true
  },
  {
    path: "/product/edit",
    name: "productEdit",
    component: productCreate,
    props: true
  },
  {
    path: "/product/create",
    name: "productCreate",
    component: productCreate,
    props: true
  },
 
  {
    path: "/rewinds",
    name: "rewindIndex",
    component: rewindIndex,
    props: false
  },
  {
    path: "/rewind/view",
    name: "rewindView",
    component: rewindView,
    props: true
  },
  {
    path: "/rewind/edit",
    name: "rewindEdit",
    component: rewindCreate,
    props: true
  },
  {
    path: "/rewind/create",
    name: "rewindCreate",
    component: rewindCreate,
    props: true
  },
 
  {
    path: "/lsds",
    name: "lsdIndex",
    component: lsdIndex,
    props: false
  },
  {
    path: "/lsd/view",
    name: "lsdView",
    component: lsdView,
    props: true
  },
  {
    path: "/lsd/edit",
    name: "lsdEdit",
    component: lsdCreate,
    props: true
  },
  {
    path: "/lsd/create",
    name: "lsdCreate",
    component: lsdCreate,
    props: true
  },

];
</script>



