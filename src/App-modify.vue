<template>
  <div>

    <FormComponents/>
      <ListData :employees="employees" />
  </div>
</template>

<script>
import ListData from './components/ListData.vue'
import FormComponents from './components/FormComponents.vue'
export default {
  name: "App",
  components: {
      ListData,
      FormComponents
  },
  data(){
      return{
          employees:[
              {name:"ก้อง",salary:15000},
              {name:"แก้ง",salary:20000},
              {name:"โก้ง",salary:30000},
              {name:"เก่ง",},
          ]
      }
  }
};
</script>

<style>
</style>
