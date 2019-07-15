<template>
  <div class=" ">
      <main-navbar></main-navbar>
      <div class="container-fluid">
      <div class="row">
      <main-sidebar></main-sidebar>
      <main-header><slot></slot></main-header>
      </div>
      </div>
  </div>
</template>

<script>
import mainNavbar from "./mainNavbar";
import mainSidebar from "./mainSidebar";
import mainHeader from "./mainHeader";
export default {
  components: {
    mainNavbar,
    mainSidebar,
    mainHeader
  }
};
</script>

<style>
</style>
