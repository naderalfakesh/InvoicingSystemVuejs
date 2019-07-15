<template>
<nav class="col-md-2 d-none d-md-block bg-light sidebar">
      <div class="sidebar-sticky">
        <ul class="nav flex-column">
          <li v-for="(link,index) in linkList" v-bind:key="index" class="nav-item">
            <router-link class="nav-link" :to="link.href" exact>
              {{link.name}} <span class="sr-only">(current)</span>
            </router-link>
          </li>
        </ul>
      </div>
    </nav>
</template>

<script>
export default {
    data: function(){
        return {
            linkList: [
             {name:"Anasayfa",href:"/"},
             {name:"Faturalar",href:"/invoices"},
             {name:"Müşteriler",href:"/companies"},
             {name:"Ürünler",href:"/products"},
             {name:"Servisler",href:"/services"},
             {name:"kontaklar",href:"/contacts"},
             {name:"çalışanlar",href:"/employees"},
             {name:"teklifler",href:"/offers"},
             {name:"Satınalmalar",href:"/purchases"},

            ]
        }
    }
}
</script>

<style>
.sidebar {
    position: fixed!important;
    top: 0;
    bottom: 0;
    left: 0;
    z-index: 100;
    padding: 48px 0 0;
    box-shadow: inset -1px 0 0 rgba(0, 0, 0, .1);
}
</style>