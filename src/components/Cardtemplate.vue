<template>
  <li>
      <img src="https://cdn-icons-png.flaticon.com/128/236/236831.png">
      <slot name="card-header"></slot>
      <slot name="card-button"></slot>
      <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {
 name:"Cardtemplate"
}
</script>

<style scoped>
li{
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: rgb(250, 157, 253);
  padding: 0.25rem;
  border-radius:15px ;
  }
  img{
      width: 100px;
      height: 100px;
  }
</style>