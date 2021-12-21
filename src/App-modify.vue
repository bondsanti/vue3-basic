<template>
  <header><h1>ระบบจัดการข้อมูลพนักงาน</h1></header>
  <form-components @save="insert" />
  <section class="emp-content" v-if="employees.length>0">
    <h2>ช้อมูลพนักงาน</h2>
    <ListData :employees="employees"/>
  </section>
</template>

<script>
import FormComponents from './components/FormComponents.vue';
import ListData from "./components/ListData.vue";

export default {
  name: "App",
  components: {
    ListData,
    FormComponents,
  },
  data(){
    return {
      employees:[]
    }
  },
  methods:{
    insert(data){
      //console.log(d);
      this.employees.push(data);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: rgb(53, 165, 77);
  color: aliceblue;
  text-align: center;
}
.emp-content {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}
.emp-content h2{
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: green;
  margin: 0 0 1rem 0;
}
</style>
