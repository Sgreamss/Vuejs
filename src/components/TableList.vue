<template>
  <div class="container">
    <h4 class="mt-5">Table of income and expenses</h4>
    <p class="lead" v-if="total<0" style="color: red">Total Value : {{total}}</p>
    <p class="lead" v-if="total>=0" style="color: green">Total Value : {{total}}</p>
    <table class="table table-dark table-hover container">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Record Name</th>
          <th scope="col">Type</th>
          <th scope="col">Date</th>
          <th scope="col">Value</th>
          <th scope="col">Details</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(rec, index) in recordList" :key="index">
          <th scope="row">{{ index + 1 }}</th>
          <td>{{ rec.name }}</td>
          <td>{{ rec.type }}</td>
          <td>{{ rec.date }}</td>
          <td>{{ rec.value }}</td>
          <td>{{ rec.detail }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      total: 0,
    };
  },
  created() {
    this.recordList.map((rec) => {
      if (rec.type === "Income") {
        this.total += parseInt(rec.value);
      }
      if (rec.type === "Expenses") {
        this.total -= parseInt(rec.value);
      }
    });
  },
  watch:{
    recordList: function(v){
      let total = 0;

      v.map((rec) => {
        if (rec.type === "Income") {
        total += parseInt(rec.value);
        }
        if (rec.type === "Expenses") {
        total -= parseInt(rec.value);
        }
      });
      this.total = total;
      console.log(total);
    }
  },

  props: ["recordList"],
};
</script>

<style>
</style>