<template>
  <div>
    <my-navbar></my-navbar>
    <div class="container-fluid">
      <div class="row">
        <my-sidebar></my-sidebar>
        <main role="main" class="col-md-9 ml-sm-auto col-lg-10 px-4">
          <router-view></router-view>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import myNavbar from "./layout/myNavbar";
import mySidebar from "./layout/mySidebar";

export default {
  components: {
    myNavbar,
    mySidebar
  }
};
</script>
