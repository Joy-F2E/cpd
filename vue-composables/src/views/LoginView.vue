<script setup lang="ts">
import { ref } from 'vue';
import { ElMessage } from 'element-plus';

  const loginModel = ref({
    username: "",
    password: ""
  })

  const user = ref();
  const login = async () => {
    user.value = { id: 1, username: loginModel.value.username }
    ElMessage.success('login success')
  }

</script>

<template>
  <h1>Login</h1>
  <div>welcome {{ user?.username }}</div>
  <el-form ref="form" :model="loginModel" label-width="80px">
    <el-form-item label="username">
      <el-input v-model="loginModel.username" placeholder="Username"></el-input>
    </el-form-item>
    <el-form-item label="password">
      <el-input v-model="loginModel.password" placeholder="Password"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="login">Login</el-button>
    </el-form-item>
  </el-form>
</template>
