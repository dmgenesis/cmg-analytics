<template>
   <app-tab-container>
      <h2 slot="header">Previous Record</h2>
      <div 
         id="service-detail"
         v-if="selectedStreamID != 0">
         <h1>Stream ID Selected : {{ selectedStreamID }}</h1>
      </div>
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
   import TabContainer from '../containers/tabContentLayout'
   import Pagination from '../shared/pagination'
   import TableList from './previousRecordTableList'
   export default {
      data () {
         return {
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
         }
      },
      components : {
         appTabContainer : TabContainer,
         appPagination : Pagination,
         appTableList : TableList
      }
   }
</script>
<style sccoped>
   #service-detail{
      background-color:#F8F9F9;
      padding: 25px 15px;
      margin:25px 0;
   }   
</style>
