<template>
  <el-form ref="loginForm" :model="loginUser" :rules="rules" class="login-form">
    <el-form-item>
      <p class="title">欢迎来到测试系统</p>
    </el-form-item>
    <el-form-item label="用户名" prop="username">
      <el-input v-model="loginUser.username" placeholder="输入用户名" />
    </el-form-item>
    <el-form-item label="密码" prop="password">
      <el-input v-model="loginUser.password" placeholder="输入密码" type="password" />
    </el-form-item>
    <el-form-item>
      <el-button type="primary" class="button" @click="login">登录</el-button>
    </el-form-item>
  </el-form>
</template>

<script lang="ts">
import { useRouter } from 'vue-router';
import { ref } from 'vue';

export default {
  setup() {
    const loginUser = ref({
      username: '',
      password: ''
    });

    const router = useRouter();

    const rules = ref({
      username: [
        { required: true, message: '请输入用户名', trigger: 'blur' },
        { pattern: /^[a-zA-Z]+$/, message: '用户名只能使用英文字母', trigger: 'blur' }
      ],
      password: [
        { required: true, message: '请输入密码', trigger: 'blur' },
        { pattern: /^[a-zA-Z0-9]+$/, message: '密码只能使用英文字母和数字', trigger: 'blur' }
      ]
    });

    const login = () => {
      if (loginUser.value.username === 'admin' && loginUser.value.password === 'admin') {
        localStorage.setItem('username', loginUser.value.username);
        localStorage.setItem('token', 'adminToken');
        router.push('/');
      } else {
        console.log('用户名或密码错误');
      }
    }

    const checkToken = () => {
      const token = localStorage.getItem('token');
      if (token) {
        router.push('/');
      }
    }

    checkToken();

    return {
      loginUser,
      rules,
      login
    }
  }
}
</script>

<style scoped>
.login-form {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 300px;
  height: 250px;
  border: 1px solid;
  border-radius: 5px;
  padding: 10px;

  .el-input {
    margin: 5px;
  }
}

.title {
  margin: 5px;
  font-size: 20px;
}
</style>
