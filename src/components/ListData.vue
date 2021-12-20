<template>
  <div>
     <ul>
         <person v-for="(item,index) in employees" :key="index" :name="item.name" :salary="item.salary"/>
     </ul>
      
 </div>

</template>

<script>
import Person from "./Person.vue";
export default {
  name: "ListData",
  components: { Person },
  data() {
    return {
      massage: "List data components",
    };
  },
  props:["employees"]
};
</script>

<style></style>
