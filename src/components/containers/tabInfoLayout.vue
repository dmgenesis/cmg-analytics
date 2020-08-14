<template>
   <div id="service-detail">
      <h3>Service Detail</h3>
      <slot></slot>
   </div>
</template>

<script>
export default {
   data() {
      return {
         
      }
   }
}
</script>

<style scoped>
   #service-detail{
      background-color:#E5E7E9;
      padding: 25px 15px;
      margin:25px 0;
   }
</style>
