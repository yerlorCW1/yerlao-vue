<script setup lang="ts">
import { reactive } from "vue";
import axios from "axios";
const data = reactive({
  id: 0,
  name: "yer",
  gender: "men",
  lastname: "lao",
  class: "cs",
  phone: "9999",
})
const saveData = async() => {
  await axios.post("http://127.0.0.1:8000/api/add-student", data).then((res) => {
    alert(res.data.status.name)
    

  })
    
  }

</script>

<template>
  <h1>ແບບຟອມລົງທະບຽນນັກສືກສາ</h1>
  <label for="">ລະຫັດນັກສືກສາ</label>
  <input type="number" v-model="data.id"><br>

  <label for="">ເພດ</label>
  <select v-model="data.gender">
    <option value="men">ຊາຍ</option>
    <option value="women">ຍີງ</option>
    <option value="men">ອື່ນໆ</option>
  </select><br>
  <label for="">ຊື່</label>
  <input type="text" v-model="data.name"><br>

  <label for="">ນາມສະກຸນ</label>

  <input type="text" v-model="data.lastname"><br>
  <label for="">ເບີໂທ</label>

  <input type="text" v-model="data.phone"><br>

  <label for="">ຫ້ອງ</label>
  <select v-model="data.class">

    <option value="ma">ma201</option>
    <option value="fns">fns201</option>
    <option value="cs">cs001</option>

  </select>
  <button @click="saveData">
    <span>ສົ່ງ</span>
  </button>

  <h1>{{ data.name }}</h1>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
