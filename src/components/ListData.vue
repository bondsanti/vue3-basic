<template>

    <ul>
      <!-- <person
        v-for="item in employees"
        :key="item.id"
        :id="item.id"
        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :isVisible="item.isVisible"
        @show="showVisible"
        @del="delEmp"
      /> -->
            <person
        v-for="(item,index) in employees"
        :key="index"

        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :skill="item.skill"

      />
    </ul>

</template>

<script>


import Person from "./Person.vue";

export default {
  name: "ListData",
  components: { Person },
  data() {
    return {
      
    };
  },
  methods: {
    // showVisible(id) {
    //   console.log(id);
    //   this.employees = this.employees.map((item) => {
    //     if (item.id === id) {
    //       return { ...item, isVisible: !item.isVisible };
    //     }
    //     return item;
    //   });
    // },
    // delEmp(id) {
    //   this.employees = this.employees.filter((item) => {
    //     return item.id !== id;
    //   });
    // },
  },
  props:["employees"]
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem;
}
</style>
