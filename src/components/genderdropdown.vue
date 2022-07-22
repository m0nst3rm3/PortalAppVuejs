<template>
  <div id="Dropdowndemo">
    <div class=" row col-sm-12">
      <div class="col-sm-4"></div>
      <div class="col-sm-4">
        <select class="form-control" @change="changevalue($event)">
          <option value="" selected disabled>Gender</option>
          <option v-for="data in rowData" :value="data.Id" :key="data.Id">{{ data.Name }}</option>
        </select>
      </div>
      <div class="col-sm-4"></div>
    </div>
    <br>
    <br>
  </div>

</template>
<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
export default {
  name: 'GenderDropDown',
  data() {
    return {
      selectedvalue: 'No Value Selected',
      seen: false,
      rowData: [{
        Name: "Male",
      }, {
        Name: "Female",
      }, {
        Name: "Others",
      }]
    }
  },
  methods: {
    changevalue(event) {
      this.selectedvalue = event.target.options[event.target.options.selectedIndex].text
      console.log(this.selectedvalue)
      this.seen = true;
    }
  }
}
</script>
<style scoped>
.form-control{
  height: fit-content;
  width: 300px;
  padding-left: 40px;
}
</style>