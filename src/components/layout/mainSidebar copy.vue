<template>
    <nav class="col-md-2 d-none d-md-block bg-light sidebar">
    <div class="sidebar-sticky">
        <ul class="nav flex-column">
        <li class="nav-item">
            <!-- <a class="nav-link " href="/view/home" :class="this.$route.name=='home' ? 'active ' : '' " > -->
            <a class="nav-link " href="/view/home"  >
            Dashboard <span class="sr-only">(current)</span>
            </a>
        </li>
        <li class="nav-item">
            <!-- <a class="nav-link" href="/view/about" :class="this.$route.name=='about' ? 'active' : '' " > -->
            <a class="nav-link" href="/view/about"  >
            About 
            </a>
        </li>
        <li class="nav-item">
            <!-- <a class="nav-link" href="/view/product" :class="this.$route.name=='product' ? 'active' : '' " > -->
            <a class="nav-link" href="/view/product"  >
            Products
            </a>
        </li>
        <li class="nav-item">
            <!-- <a class="nav-link" href="/view/company" :class="this.$route.name=='company' ? 'active' : '' " > -->
            <a class="nav-link" href="/view/company"  >
            Companies
            </a>
        </li>
        <li class="nav-item">
            <!-- <a class="nav-link" href="/view/contact" :class="this.$route.name=='contact' ? 'active' : '' " > -->
            <a class="nav-link" href="/view/contact"  >
            Contacts
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">
            Customers
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">
            Reports
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">
            Integrations
            </a>
        </li>
            <!-- <router-link v-for="(rout,index) in routlist" v-bind:key="index" :to="rout.path" >{{rout.name}}</router-link> -->

        </ul>

        <h6 class="sidebar-heading d-flex justify-content-between align-items-center px-3 mt-4 mb-1 text-muted">
        <span>Saved reports</span>
        <a class="d-flex align-items-center text-muted" href="#">
        </a>
        </h6>
        <ul class="nav flex-column mb-2">
        <li class="nav-item">
            <a class="nav-link" href="#">
            Current month
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">
            Last quarter
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">
            Social engagement
            </a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">
            Year-end sale
            </a>
        </li>
        </ul>
    </div>
</nav>
</template>

<script>
export default {
    data: function(){
        return {
            routlist: [
             {name:"home",path:"/"}   
            ]
        }
    }
}
</script>

<style>

</style>