<template>
  <el-container style="padding: 0; margin: 0;">
    <el-container style="padding: 0; margin: 0;">
      <el-header style="padding: 0; margin: 0;">
        <Header />
      </el-header>
      <el-main style="padding: 0; margin: 0;">
        <router-view />
      </el-main>
    </el-container>
  </el-container>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import Header from '@/components/HeaderView.vue';

export default defineComponent({
  name: 'HomeView',
  components: {
    Header,
  },
});
</script>
<style scoped>
</style>
