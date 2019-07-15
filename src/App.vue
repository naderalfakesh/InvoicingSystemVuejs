<template>
  <div id="app" class=" ">
      <main-frame >
        <router-view></router-view>
        
      </main-frame>
      <!-- <router-view name="invoice"></router-view> -->
      
  </div>
</template>

<script>
import mainFrame from "./components/layout/mainFrame";
export default {
  name: "app",
  components: {
    mainFrame
  }
};
</script>

<style>

</style>
