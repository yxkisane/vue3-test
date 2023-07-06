<template>
    <div class="header">
        <el-menu :default-active="activeIndex" router mode="horizontal" :ellipsis="false" @select="handleSelect">
            <el-menu-item index="/search">资源大厅</el-menu-item>
            <div class="flex-grow" />
            <el-sub-menu index="0">
                <template #title><el-icon :size="40">
                        <User />
                    </el-icon>个人中心</template>
                <el-menu-item index="0-1" @click="handleLogout">退出登陆</el-menu-item>
            </el-sub-menu>
        </el-menu>
    </div>
  </template>
  <script lang="ts">
  import { defineComponent } from 'vue';
  import { ref } from 'vue'
  import { useRouter } from 'vue-router'
  
  export default defineComponent({
    name: 'HeaderView',
    setup() {
        const activeIndex = ref('/search');
        const router = useRouter();
        const handleSelect = (key: string, keyPath: string[]) => {
            console.log(key, keyPath)
        };
        const handleLogout = () => {
            localStorage.removeItem('token');
            router.push('/login');
        }
        return {
            activeIndex, handleSelect, handleLogout
        }
  
    }
  });
  </script>
  <style scoped>
  .flex-grow {
    flex-grow: 1;
  }
  .header {
    height: 50px;
  }
  </style>
  