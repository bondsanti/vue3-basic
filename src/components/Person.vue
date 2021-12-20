<template>
  <div>
    <h1>ชื่อ : {{ name }} || เงินเดือน : {{ salary }}</h1>
  </div>
</template>

<script>
export default {
  name: "Person",
  props: {
    name: {
      type: String,
      required: true,
    },
    salary:{
        type:Number,
        default:10000
    }
  },
};
</script>

<style scoped>
h1 {
  color: brown;
}
</style>
