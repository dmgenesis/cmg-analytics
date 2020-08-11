<template>
   <div>
      <table class="table">
         <tr>
            <th>Date</th>
            <th>Service Name</th>
            <th>Title</th>
            <th>Speaker</th>
            <th>Views</th>
            <th>Countries</th>
            <th></th>
         </tr>
         <tr class="service-details"
            v-for="service in services"
            @click="selectStream(service.id)">
            <td></td>
            <td>{{ service.serviceName }}</td>
            <td>{{ service.serviceTitle }}</td>
            <td>{{ service.speaker }}</td>
            <td>{{ service.views }}</td>
            <td>{{ service.countries }}</td>
            <td>
               <button class="btn btn-primary btn-sm">Delete</button>
            </td>
         </tr>
      </table>
   </div>
</template>

<script>
export default {
   data(){
      return {
         services : [
            {
               id : 1,
               serviceName : 'Sunday Service',
               serviceTitle : 'I Will Meet you there Pt. 20',
               speaker : 'Bro. Danny del Mundo',
               views : 35,
               countries : 3
            },
            {
               id : 2,
               serviceName : 'Wednesday Service',
               serviceTitle : 'I Will Meet you there Pt. 19',
               speaker : 'Bro. Danny del Mundo',
               views : 21,
               countries : 5
            },
            {
               id : 3,
               serviceName : 'Sunday Service',
               serviceTitle : 'I Will Meet you there Pt. 18',
               speaker : 'Bro. Danny del Mundo',
               views : 65,
               countries : 5
            },
            {
               id : 4,
               serviceName : 'Wednesday Service',
               serviceTitle : 'I Will Meet you there Pt. 17',
               speaker : 'Bro. Danny del Mundo',
               views : 35,
               countries : 3
            },
            {
               id : 5,
               serviceName : 'Sunday Service',
               serviceTitle : 'I Will Meet you there Pt. 16',
               speaker : 'Bro. Danny del Mundo',
               views : 45,
               countries : 7
            },
         ]
      }
   },
   methods : {
      selectStream(id) {
         this.$emit('selectChurch', id)
      }
   }
}
</script>
<style>
   .table{
      font-size:14px;
   }
   tr.service-details:hover{
      background-color:#F4F6F6;
   }
</style>
