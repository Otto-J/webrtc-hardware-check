<template>
  <div id="page">about</div>
  <div>str 是 {{ str }}</div>
  <div>name 是 {{ obj.name }}</div>
  <div>时间 {{time}}</div>
  <button @click="changeN">name加个装饰</button>
  <button @click="changeM">str加个装饰</button>
</template>
<script lang="ts">
import { ref, reactive, onMounted } from 'vue';
import { changeName } from './changeName';
export default {
  name: 'About',
  setup() {
    const str = ref('go');
    const obj = reactive({
      name: 'xb',
    });

    const time = ref(new Date().toLocaleString());

    const changeM = () => {
      str.value = 'x';
    };

    // onMounted()=>{
    //   setInterval(()=>{
    //     time.value = new Date().toLocaleString()
    //   },1000)
    // }

    const changeN = () => {
      obj.name = changeName(obj.name);
    };

    return {
      str,
      obj,
      changeN,time,
      changeM,
    };
  },
};
</script>
<style lang="less">
#page {
  color: red;
  &:hover{
     color: rgb(22, 167, 111) 
  }
}
</style>
