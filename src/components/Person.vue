<template>
  <Cardtemplate>
    <template v-slot:card-header>
      <h1>ชื่อ : {{ name }}</h1>
    </template>
    <!-- <template v-slot:card-button>
      <button @click="showDetail(id)">
        {{ isVisible ? "ซ่อน" : "ดู" }} รายละเอียด
      </button>
      &nbsp;
      <button @click="deleteItems(id)">ลบข้อมูล</button>
    </template> -->
    <!-- <template v-slot:card-content>
      <transition name="fade">
        <div v-show="isVisible">
          <p>ตำแหน่งงาน : {{ department }} || เงินเดือน : {{ salary }}.-</p>
        </div>
      </transition>
    </template> -->
        <template v-slot:card-content>
      <transition name="fade">
        <div>
          <p>ตำแหน่งงาน : {{ department }} || เงินเดือน : {{ salary }}.-</p>
           <p>ทักษะด้านภาษา :{{ skill }}</p>
        </div>
      </transition>
    </template>
  </Cardtemplate>
</template>

<script>
import Cardtemplate from "./Cardtemplate.vue";

export default {
  components: { Cardtemplate },
  name: "Person",
  props: {
    id: {
      type: Number,
    },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 10000,
    },
    department: {
      type: String,
      required: true,
    },
        skill: {
      type: String,
      required: true,
    },
    // isVisible: {
    //   type: Boolean,
    // },
  },
  methods: {
    // showDetail(id) {
    //   //console.log(id)
    //   this.$emit("show", id);
    // },
    // deleteItems(id) {
    //   this.$emit("del", id);
    // },
  },
};
</script>

<style scoped>
h1 {
  color: rgb(255, 255, 255);
}
/* li{
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: rgb(157, 242, 253);
  padding: 0.25rem;
  border-radius:15px ;
  } */
button {
  cursor: pointer;
  border: 1px solid firebrick;
  border-radius: 15px;
  color: rgb(0, 0, 0);
  padding: 0.05rem 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
