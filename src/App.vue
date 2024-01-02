<template>
  <t-button @click="visible = true">打开</t-button>
  <t-dialog v-model:visible="visible" title="demo" width="800px" :headerAffixedTop="{ offsetTop: 200, zIndex: 30000 }">
    <t-table row-key="id" :bordered="true" :data="data" :columns="columns"> </t-table>
  </t-dialog>
</template>

<script setup>
import { ref } from 'vue'

const visible = ref(false)

const data = ref([])

for (let i = 0; i < 20; i++) {
  data.value.push({
    id: 'id' + i,
    name: 'name' + i,
    age: 'age' + i,
    gender: 'gender' + i,
    address: 'address' + i,
    phone: 'phone' + i,
    email: 'email' + i,
  })
}

const columns = [
  { colKey: 'id', title: 'ID', align: 'center' },
  { colKey: 'name', title: '姓名', align: 'center' },
  { colKey: 'age', title: '年龄', align: 'center' },
  { colKey: 'gender', title: '性别', align: 'center' },
  { colKey: 'address', title: '地址', align: 'center' },
  { colKey: 'phone', title: '手机号', align: 'center' },
  { colKey: 'email', title: '邮箱', align: 'center' },
]
</script>
