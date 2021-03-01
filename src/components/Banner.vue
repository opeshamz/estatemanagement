<template>
  <div class="banner" id="Banner">
   <div class="">
     

   </div>
  </div>
</template>
<script>
export default {
  name: "Banner",
};

</script>


<style scoped>
.banner {
  max-height: auto;
  display: flex;
  height: 750px;
  background: url("../assets/banner1.jpg") no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  background-color: #6ec1e4;
  background-repeat: no-repeat;
  clip-path: polygon(100% 0, 100% 84%, 82% 100%, 15% 100%, 22% 90%, 0 90%, 0 0);
  background-blend-mode: luminosity;
  opacity: 0.81;
  text-align: center ;
}
</style>
