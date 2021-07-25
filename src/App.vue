<template>
  <div>
    <h1 class="container">Record of Income and Expenses</h1>
    <input-form v-bind:addRecordList="addRecordList"></input-form>
    <table-list v-bind:recordList="recordList"></table-list>
  </div>
</template>

<script>

import TableList from '@/components/TableList.vue'
import InputForm from './components/InputForm.vue'
import datajson from '../data.json'


export default {
  
  components: {
    TableList,
    InputForm,
    
  },
  
  created(){
    let temrecordList = [...datajson.recordList];
    this.recordList = temrecordList;
  },
  
  data(){
    return{
      recordList:[],
    };
  },
  
  methods:{
    addRecordList(record){
      let temrecordList = [...this.recordList,record];
      this.recordList = temrecordList;
    }
  }
}
</script>

<style>

</style>
