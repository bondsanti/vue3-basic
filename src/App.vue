<template>
  <section>
    <img :src="profile_img" :width="size" :height="size"/>
    <h2>Name : {{gerFullname()}}</h2>
    Nick name : <input type="" v-on:input="setNickname">
    <h3>my nickname : {{nickname}} </h3>
      <p>Age : {{age}} </p>
    <p>Address : <span v-html="address"></span></p>
    <a :href="social" target="_blank">Facebook</a>
    <p>hobby :</p>
      <ol>
        <li>{{hobby[0]}}</li>
        <li>{{hobby[1]}}</li>
        <li>{{hobby[2]}}</li>
      </ol>
          <p>ข้อมูลพื้นฐาน :</p>
      <ui>
        <li>gander : {{general.gander}}</li>
        <li>weight :{{general.weight}}</li>
        <li>status :{{general.status}}</li>
      </ui>
  <button @click="showData">ดูข้อมูล</button>
  <button @click="plusAge">เพิ่ม อายุ</button>
  <button @click="minusAge">ลด อายุ</button>
  </section>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      nickname:"",
      firstName:"Santi ",
      lastName:"Chooprayoon",
      age:100,
      address:"<strong>เยอร์มัน</storng>",
      profile_img:"https://st.depositphotos.com/1052233/2885/v/600/depositphotos_28850541-stock-illustration-male-default-profile-picture.jpg",
      size:150,
      social:"https://www.facebook.com/bondsanti",
      hobby:["ทำสวน","เล่นเกม","ฟังเพลง"],
      general:{
        gander:"ชาย",
        weight:82.5,
        height:170,
        status: true
      }
    }
  },
  methods:{
    gerFullname(){
     // return this.firstName + this.lastName
      return `${this.firstName +" "+ this.lastName}`
    },
    showData(){
      alert(this.firstName)
    },
    plusAge(){
      this.age++
    },
    minusAge(){
      this.age--
    },
    setNickname(e){
     // console.log(e.target.value);
     this.nickname=e.target.value;
    }
  }

}
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
