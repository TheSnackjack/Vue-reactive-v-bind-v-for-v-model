<script setup>
import { reactive } from 'vue';

const genderList = ['ชาย', 'หญิง', 'ไม่ระบุ']
const interList = ['เกม', 'กีฬา', 'หนัง']

const formData = reactive({
  fname: (''),
  lname: (''),
  gender: (''),
  inter: []
})

const Submit = () => {
  console.log('formData', formData)
}

</script>

<template>
  <div class="header">
    <h1>Vue Leaning</h1>
    <h2>reactive v-bind v-for v-model</h2>
  </div>
  <div class="content">
    <div>
      <div>ชื่อ</div>
      <input type="text" name="fname" v-model="formData.fname">
    </div>
    <div>
      <div>นามสกุล</div>
      <input type="text" name="lname" v-model="formData.lname">
    </div>
    <div>
      <div>เพศ</div>
      <div v-for="gender in genderList">
        <input type="radio" name="gender" v-bind:value="gender" v-model="formData.gender"> {{ gender }}
      </div>
    </div>
    <div>
      <div>ความสนใจ</div>
      <div v-for="inter in interList">
        <input type="checkbox" name="inter" v-bind:value="inter" v-model="formData.inter">{{ inter }}
      </div>
    </div>
    <button style="margin-top: 24px;" @click="Submit">Submit</button>
  </div>
</template>

<style>
.content {
  display: flex;
  flex-direction: column;

}
</style>