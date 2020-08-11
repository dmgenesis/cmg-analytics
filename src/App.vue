<template>
   <div id="app-container">
      <div class="container">
         <ul id="tab-header">
            <li 
               class="tab-list"
               :class="{ active : isLive }"
               @click="isLive = true">
               Active
               </li>
            <li 
               class="tab-list"
               :class="{ active : !isLive }"
               @click="isLive = false">
               Previous
            </li>
         </ul>
         <div id="tab-content">
            <app-tab-container
            v-if="isLive == true">
               <h2 slot="header">Current Live Stream</h2>
               <h1>This Content is for Live Stream Analytics</h1>
            </app-tab-container>
            <div v-else>
               <app-previous-record></app-previous-record>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
import TabContainer from './components/containers/tabContentLayout'
import PreviousRecord from './components/analytics/previousRecord'

export default {
  data () {
    return {
      isLive : false
    }
  },
  components : {
     appTabContainer : TabContainer,
     appPreviousRecord : PreviousRecord
  }
}
</script>

<style scoped>
   #app-container{
      padding: 100px 0 60px;
      background-color:#dee2e6;
      min-height: 100vh;
   }
   ul#tab-header{
      padding: 0;
      margin:0;
      display: flex;
      list-style-type:none;
   }

   ul#tab-header li.active{
      background-color:#fff;
      border-top:solid 3px #007bff;
   }
   ul#tab-header li{
      padding: 15px 40px;
      background-color: #F8F9F9;
      border-top:solid 3px #fff;
      margin: 0 5px 0 0;
      color:#000;
      text-decoration: none;
      text-transform: uppercase;
   }
   ul#tab-header li:hover{
      background-color:#fff;
   }
   #tab-content{
      background-color:#fff;
      padding:40px 25px;
   }
</style>
