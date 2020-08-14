<template>
   <app-tab-container>
      <ul id="service-report-option">
         <li
            :class="{active : pageView == 'last-seven'}">
            <a href="#" @click.prevent="pageView = 'last-seven'">Last 7 Streams</a>
         </li>
         <li 
            :class="{active : pageView == 'summary'}">
            <a href="#" @click.prevent="pageView = 'summary'">Service Summary</a>
         </li>
         <li
            :class="{active : pageView == 'last-thirty'}">
            <a href="#" @click.prevent="pageView = 'last-thirty'">Last 30 days</a>
         </li>
      </ul>
      <app-tab-layout
         v-show="pageView == 'summary'">
         <app-service-details></app-service-details>
      </app-tab-layout>
      <app-tab-layout
         v-show="pageView == 'last-seven'">
         <h5>Last 7</h5>
      </app-tab-layout>
       <app-tab-layout
         v-show="pageView == 'last-thirty'">
         <h5>Last Thirty</h5>
       </app-tab-layout>
      <div>
         <app-pagination
            :selected="selectedPage"
            :totalPage="totalPage"
            @changePage="updatePage"
            ></app-pagination>
         <app-table-list
            @selectChurch="selectStream"></app-table-list>
         <app-pagination
            :selected="selectedPage"
            :totalPage="totalPage"
            @changePage="updatePage"
            ></app-pagination>
      </div>
   </app-tab-container>
</template>
<script>
   // Layouts 
   import TabInfoLayout from '../containers/tabInfoLayout'
   // Components
   import TabContainer from '../containers/tabContentLayout'
   import Pagination from '../shared/pagination'
   import TableList from './previousRecordTableList'
   import ServiceDetails from './serviceDetails'

   export default {
      props : {
      },
      data () {
         return {
            pageView : 'last-seven',
            totalPage : 12,   
            selectedPage : 1,
            selectedStreamID : 0
         }
      },
      methods : {
         updatePage($event) {
            this.selectedPage = $event
         },
         selectStream($event) {
            this.selectedStreamID = $event
            this.pageView = 'summary'
         }
      },
      components : {
         appTabContainer : TabContainer,
         appPagination : Pagination,
         appTableList : TableList, 
         appServiceDetails : ServiceDetails,
         appTabLayout : TabInfoLayout
      }
   }
</script>
<style scoped>
   ul#service-report-option{
      display: flex;
      padding: 0;
      list-style-type:none;
      color:#cdcdcd;
   }
   ul#service-report-option li a{
      color: #cdcdcd;
      font-size: 14px;
      text-transform: uppercase;
      margin-right: 10px;
   }
   ul#service-report-option li.active a{
      font-weight:400;
      color: #000;
   }
   ul#service-report-option li a:hover{
      color:#007bff; 
      text-decoration: none;
   }   
</style>
