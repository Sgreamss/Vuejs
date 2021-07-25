<template>
  <div>
    <h1 class="container">Record of Income and Expenses</h1>
    <input-form></input-form>
    <table-list></table-list>
  </div>
</template>

<script>

import TableList from '@/components/TableList.vue'
import InputForm from './components/InputForm.vue'


export default {
  name: 'Table',
  components: {
    TableList,
    InputForm
    
  }
}
</script>

<style>

</style>
