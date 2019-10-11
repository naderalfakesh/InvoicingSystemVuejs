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
import offerIndex from "./components/offers/offerIndex";
import offerView from "./components/offers/offerView";
import offerCreate from "./components/offers/offerCreate";
import nameplateIndex from "./components/nameplates/nameplateIndex";
import nameplateView from "./components/nameplates/nameplateView";
import nameplateCreate from "./components/nameplates/nameplateCreate";
import purchaseIndex from "./components/purchases/purchaseIndex";
import purchaseView from "./components/purchases/purchaseView";
import purchaseCreate from "./components/purchases/purchaseCreate";
import serviceIndex from "./components/services/serviceIndex";
import serviceView from "./components/services/serviceView";
import serviceCreate from "./components/services/serviceCreate";

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

  {
    path: "/offers",
    name: "offerIndex",
    component: offerIndex,
    props: false
  },
  {
    path: "/offer/view",
    name: "offerView",
    component: offerView,
    props: true
  },
  {
    path: "/offer/edit",
    name: "offerEdit",
    component: offerCreate,
    props: true
  },
  {
    path: "/offer/create",
    name: "offerCreate",
    component: offerCreate,
    props: true
  },

  {
    path: "/nameplates",
    name: "nameplateIndex",
    component: nameplateIndex,
    props: false
  },
  {
    path: "/nameplate/view",
    name: "nameplateView",
    component: nameplateView,
    props: true
  },
  {
    path: "/nameplate/edit",
    name: "nameplateEdit",
    component: nameplateCreate,
    props: true
  },
  {
    path: "/nameplate/create",
    name: "nameplateCreate",
    component: nameplateCreate,
    props: true
  },

  {
    path: "/purchases",
    name: "purchaseIndex",
    component: purchaseIndex,
    props: true
  },
  {
    path: "/purchase/view",
    name: "purchaseView",
    component: purchaseView,
    props: true
  },
  {
    path: "/purchase/edit",
    name: "purchaseEdit",
    component: purchaseCreate,
    props: true
  },
  {
    path: "/purchase/create",
    name: "purchaseCreate",
    component: purchaseCreate,
    props: true
  },

  {
    path: "/services",
    name: "serviceIndex",
    component: serviceIndex,
    props: true
  },
  {
    path: "/service/view",
    name: "serviceView",
    component: serviceView,
    props: true
  },
  {
    path: "/service/edit",
    name: "serviceEdit",
    component: serviceCreate,
    props: true
  },
  {
    path: "/service/create",
    name: "serviceCreate",
    component: serviceCreate,
    props: true
  },
  
];
</script>



