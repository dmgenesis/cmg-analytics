<template>
   <table class="table">
      <tr>
         <th>Username</th>
         <th>Name</th>
         <th>Countries</th>
      </tr>
      <tr v-for="user in users">
         <td>{{ user.username }}</td>
         <td>{{ user.name }}</td>
         <td>{{ user.country }}</td>
      </tr>
   </table>
</template>

<script>
export default {
   data() {
      return {
         users : [
            {
               id : 1,
               name : 'Genesis del Mundo',
               username : 'dmgenesis',
               country : 'Philippines'
            },
             {
               id : 2,
               name : 'Billy Tebo',
               username : 'btebo',
               country : 'United States'
            },
             {
               id : 3,
               name : 'Micha del Mund',
               username : 'dmMicha',
               country : 'Philippines'
            },
             {
               id : 4,
               name : 'Daniel del Mundo',
               username : 'dmdaniel',
               country : 'Philippines'
            }
         ]
      }
   }
}
</script>

<style>

</style>
