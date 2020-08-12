<template>
   <div id="service-details-container">
      <div id="service-info">
         <p>Service Name <small> Date </small> </p>
         <p>Title : I will meet you in there </p>
         <p>Speaker : Bro. Danny del Mundo </p>
         <p>Duration : 1 hour 34 minutes </p>
         <p>Views : 
            <a href="#" @click.prevent="isViewUsers = true">65</a>
         </p>
         <p>Countries : 
            <a href="#" @click.prevent="isViewUsers = false">3</a>
         </p>
      </div>
      <div id="service-viewers-info">
         <ul id="view-tab-header">
            <li
               :class="{ selected : isViewUsers }" 
               @click="isViewUsers = true">Users</li>
            <li
               :class="{ selected : !isViewUsers }" 
               @click="isViewUsers = false">Countries</li>
         </ul>
         <div id="view-tab-content">
            <div v-show="isViewUsers == true">
               <h5>Users</h5>
               <app-users-table></app-users-table>
            </div>
            <div v-show="isViewUsers == !true">
               <h5>Countries</h5>
               <app-countries-table></app-countries-table>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
import UsersTableList from './streamDetailsUsers'
import CountriesTableList from './streamDetailsCountry'

export default {
   props : {

   },
   data () {
      return {
         isViewUsers : true
      }
   },
   methods : {

   },
   components : {
      appUsersTable : UsersTableList,
      appCountriesTable : CountriesTableList
   }
}
</script>

<style>
   #service-details-container{
      display: flex;
      justify-content: space-evenly;
   }
   #service-info{
      width: 40%;
   }
   #service-viewers-info{
      width: 55%;
      padding-left: 15px;
      border-left: 1px solid #cdcdcd;
   }
   ul#view-tab-header{
      display: flex;
      list-style-type:none;
      padding: 0;
      margin: 0;
   }
   ul#view-tab-header li{
      padding: 5px 15px 5px;
      font-size: 12px;
      text-transform: uppercase;
      background-color:#fff;
      margin:0 5px 0 0;
   }
   ul#view-tab-header li.selected{
      font-weight: 600;
   }
   #view-tab-content{
      background-color:#fff;
      padding: 15px 10px;
   }

</style>
