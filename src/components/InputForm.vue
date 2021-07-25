<template>
  <div >
      <h4 class="container mb-3">Input Form</h4>
      <div class="container">
        
        <form class="row gx-3 gy-2 align-items-center">
            <div class="col-sm-3 ">
                <label class="visually-hidden">Name</label>
                <input type="text" class="form-control" id="inputName" 
                v-model="name" placeholder="Record Name" required>
            </div>
            <div class="col-sm-3">
                <label class="visually-hidden">Type Select</label>
                <select class="form-select" id="typeSelect" required>
                    <option selected>Choose Type</option>
                    <option value="1">Income</option>
                    <option value="2">Expenses</option>
                </select>
            </div>
            <div class="col-sm-3">
                <label class="me-3">Date :</label>
                <input  type="date" id="dateSelect" required>
            </div>
        </form>
        
        <form class="row gx-3 gy-2 mt-1 align-items-center">
            <div class="col-sm-3">
                <label class="visually-hidden">Value</label>
                <input type="number" class="form-control" id="inputValue" 
                v-model="value" placeholder="Value" required>
                <div id="valueHelp" class="form-text">Value must be number.</div>
            </div>
            <div class="col-sm-6">
                <label class="visually-hidden">Details</label>
                <input type="text" class="form-control" id="inputDetail" 
                v-model="detail" placeholder="Detail">
                <div id="detailHelp" class="form-text">Details is optional. (You can leave it blank)</div>
            </div>
        </form>
        
        <button class="btn btn-outline-dark mt-3" type="submit"
                @click = "submitForm">
            Submit
        </button>

      </div>
  </div>

</template>

<script>
export default {
    data(){
        return{
            name: '',
            type: '',
            date: '',
            value: '',
            detail: '',
        }
    },
    methods: {
        submitForm(){
            
        }
    }
}
</script>

<style>

</style>