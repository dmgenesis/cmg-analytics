<template>
   <ul id="pagination-component">
      <li v-for="page in totalPage"> 
         <a href="#"
            :class="{selected : page == selected}"
            @click.prevent="selectPage(page)">{{ page }}</a>
      </li>
   </ul>
</template>
<script>
export default {
   props : {
      selected : Number,
      totalPage : Number
   },
   methods : {
      selectPage(pageSelected) {
         this.currentPage = pageSelected
         this.$emit('changePage', pageSelected)
      }
   }
}
</script>

<style>
   ul#pagination-component{
      display: flex;
      list-style-type:none;
      padding:0;
      margin:0 0 25px 0;
      font-size:12px;
   }
   ul#pagination-component li{
      padding: 5px 15px;
   }
   ul#pagination-component li a{
      color:#cdcdcd
   }
   ul#pagination-component li a.selected{
      color:#000;
   }
   ul#pagination-component li a:hover{
      color:#007bff;
      text-decoration: none
   }
</style>
