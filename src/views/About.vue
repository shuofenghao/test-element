<template>
  <el-container>
    <el-header class="AboutHeader">
      质量任务
    </el-header>
    <el-row>
      <AboutForm />
    </el-row>
    <el-row>
      <AboutTable />
    </el-row>
  </el-container>
</template>

<script>
  import AboutForm from '@/components/AboutForm';
  import AboutTable from "@/components/AboutTable";

  export default {
    name: 'About',
    components: {
      AboutTable,
      AboutForm,
    },
  }
</script>

<style>
  .AboutHeader {
    text-align: left;
    line-height: 60px;
    background-color: rgba(0, 0, 0, 0.3);
    font-size: 1.1em;
  }
</style>
