<template>
  <form @submit.prevent="submitForm">
    <div class="form-control">
      <label for="emp-name">ชื่อพนักงาน</label>
      <input type="text" v-model.trim="employee.name" />
    </div>
    <div class="form-control">
      <label for="emp-salary">เงินเดือน</label>
      <input type="number" v-model="employee.salary" />
    </div>
    <div class="form-control">
      <label for="emp-department">ตำแหน่ง</label>
      <select v-model="employee.department">
        <option value="โปรแกรมเมอร์">โปรแกรมเมอร์</option>
        <option value="ธุรการ">ธุรการ</option>
        <option value="บัญชี">บัญชี</option>
        <option value="การตลาด">การตลาด</option>
      </select>
    </div>
    <div class="form-control">
      <label for="">เพศ</label>
      <input type="radio" value="ชาย" v-model="employee.gander" />
      <label for="emp-gander">ชาย</label>
      <input type="radio" value="หญิง" v-model="employee.gander" />
      <label for="emp-gander">หญิง</label>
    </div>
    <div class="form-control">
      <label for="">ทักษะด้านภาษา</label>
      <input type="checkbox" value="อังกฤษ" v-model="employee.skill" />
      <label for="emp-skill">อังกฤษ</label>
      <input type="checkbox" value="จีน" v-model="employee.skill" />
      <label for="emp-skill">จีน</label>
      <input type="checkbox" value="เกาหลี" v-model="employee.skill" />
      <label for="emp-skill">เกาหลี</label>
    </div>
    <div>
      <button>บันทึกข้อมูล</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "FormComponents",
  data() {
    return {
      employee: {
        name: "",
        salary: 0,
        department: "",
        gander: "",
        skill: [],
      },
    };
  },
  methods: {
    submitForm() {
      // console.log(this.employee)
      const newEmployee = {
        name: this.employee.name,
        salary: this.employee.salary,
        department: this.employee.department,
        gander: this.employee.gander,
        skill: this.employee.skill,
      };
      this.$emit("save", newEmployee);
      this.resetForm();
    },
    resetForm(){
        this.employee.name="";
        this.employee.salary=0
        this.employee.department=""
        this.employee.gander=""
        this.employee.skill=[]
    }
  },
};
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
  padding: 2rem;
  background: rgb(225, 228, 221);
}
.form-control {
  margin: 0.5rem 0;
}
label {
  font-weight: bold;
}
input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}
button {
  font: inherit;
  background: green;
  color: white;
  cursor: pointer;
  padding: 0.25rem 1rem;
  border-radius: 10px;
}
input[type="radio"] {
  display: inline-block;
  width: auto;
  margin-right: 0.5rem;
}
input[type="radio"] + label {
  font-weight: normal;
}
input[type="checkbox"] {
  display: inline-block;
  width: auto;
  margin-right: 0.5rem;
}
input[type="checkbox"] + label {
  font-weight: normal;
}
</style>
