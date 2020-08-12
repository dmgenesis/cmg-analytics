<template>
   <table class="table">
      <tr>
         <th>Country</th>
         <th>Views</th>
      </tr>
      <tr v-for="country in countries">
         <td>{{ country.name }}</td>
         <td>{{ country.views }}</td>
      </tr>
   </table>
</template>

<script>
export default {
   data () {
      return {
         countries : [
            {
               name : 'Philippines',
               views : 34
            },
            {
               name : 'United States',
               views : 21
            },
            {
               name : 'Japan',
               views : 2
            }
         ]
      }
   }
}
</script>

<style>

</style>
