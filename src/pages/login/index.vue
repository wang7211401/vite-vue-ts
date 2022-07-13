import { ref } from 'vue';
<template>
  <div>登录页面</div>
  <p>{{ msg }}</p>

  <hello-world-vue msg="hello world"></hello-world-vue>

  <div>用户名:{{ mainStore.name }}<br />长度:{{ mainStore.nameLength }}</div>
  <hr />
  <button @click="updateName">修改store中的name</button>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import HelloWorldVue from '../../components/HelloWorld.vue'
import { useMainStore } from '@/store/main'
const msg = ref('信息')
const mainStore = useMainStore()

const updateName = () => {
  // mainStore.$patch({
  //     name:"名称修改了" + parseInt(Math.random() * 10000 + "")
  // })
  mainStore.insertPost('名称修改了' + parseInt(Math.random() * 10000 + ''))
}
</script>

<style lang="scss" scoped>
p {
  color: $test-color;
}
</style>
