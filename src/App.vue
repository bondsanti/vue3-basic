<template>
  <section>
    <img :src="profile_img" :width="size" :height="size" ref="imageURL" />
    <h2>Name : {{ getFullname }}</h2>
    <!-- Nick name : <input type="" v-on:input="setNickname"> -->
    <form @submit="saveData">
      <label> ป้อนชื่อเล่น : </label><input type="" ref="NicknameEl" />
      <button type="submit">ตกลง</button>
    </form>

    <h3>my nickname : {{ nickname }}</h3>
    <h3>เงินเดือน : {{ salary }}บาท ,รายได้/ปี : {{ getIncome }}บาท</h3>
    <h3>ตำแหน่ง : {{ getPositon }}</h3>
    <button @click="addSalary(1000)">เพิ่มเงินเดือน</button>
    <button @click="minusSalary(1000)">ลดเงินเดือน</button>
    <p>================</p>
    <h4>RandomBymedtod(1) : {{ getRandomByMedtod() }}</h4>
    <h4>RandomBymedtod(2) : {{ getRandomByMedtod() }}</h4>
    <h4>RandomByComputed(1) : {{ getRandomByComputed }}</h4>
    <h4>RandomByComputed(2) : {{ getRandomByComputed }}</h4>

    <button @click="clickShowDetail">
      {{ showArticle ? "[ซ่อน]" : "[แสดง]" }} รายละเอียด
    </button>
    <article v-show="showArticle">
      <p>Age : {{ age }}</p>
      <p>Address : <span v-html="address"></span></p>
      <a :href="social" target="_blank">Facebook</a>

      <p v-if="hobby.length === 0" class="text-red">Not hobby :</p>
      <div v-else>
        <p>hobby :</p>
        <ol>
          <li v-for="(item, index) in hobby" :key="index">{{ item }}</li>
        </ol>
      </div>
      <p>ข้อมูลพื้นฐาน :</p>
      <ui>
        <li v-for="(item, key) in general" :key="key">
          {{ key }} : {{ item }}
        </li>
      </ui>
      <button @click="showData">ดูข้อมูล</button>
      <button @click="plusAge">เพิ่ม อายุ</button>
      <button @click="minusAge">ลด อายุ</button>
    </article>

    <p>-------------------------</p>
  </section>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      nickname: "",
      firstName: "Santi ",
      lastName: "Chooprayoon",
      salary: 10000,
      age: 100,
      address: "<strong>เยอร์มัน</storng>",
      profile_img:
        "https://st.depositphotos.com/1052233/2885/v/600/depositphotos_28850541-stock-illustration-male-default-profile-picture.jpg",
      size: 150,
      social: "https://www.facebook.com/bondsanti",
      hobby: ["ว่ายน้ำ", "ยิงปืน", "อ่านหนังสือ"],
      general: {
        gander: "ชาย",
        weight: 82.5,
        height: 170,
        status: true,
      },
      showArticle: false,
    };
  },
  methods: {
    showData() {
      alert(this.firstName);
    },
    plusAge() {
      this.age++;
    },
    minusAge() {
      this.age--;
    },
    getRandomByMedtod() {
      return Math.random();
    },
    // setNickname(e){
    //  // console.log(e.target.value);
    //  this.nickname=e.target.value;
    // },
    saveData(e) {
      e.preventDefault(); // เมื่อกด save แล้ว จะไม่เคลียร์ข้อมูลใน Form
      this.nickname = this.$refs.NicknameEl.value;
      alert("บันทึกเรียบร้อย");
      console.log(this.$refs.imageURL);
    },
    clickShowDetail() {
      this.showArticle = !this.showArticle;
    },
    addSalary(value) {
      this.salary += value;
    },
    minusSalary(value){
      this.salary -= value
    }
  },
  computed: {
    getFullname() {
      // return this.firstName + this.lastName
      return `${this.firstName + " " + this.lastName}`;
    },
    getRandomByComputed() {
      return Math.random();
    },
    getIncome() {
      return this.salary * 12;
    },
    getPositon() {
      return this.salary >= 25000 ? "โปรแกรมเมอร์" : "ธุรการ";
    },
  },
  watch:{
    //ติดตามค่าหรือข้อมูล
    salary(value){
      if(value>30000){
        alert("เงินเดือนไม่ควรเกิน 30,000 บาท");
        setTimeout(()=>{
          this.salary=30000
        },1000)
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
