<template>
  <div>
    <el-row
      type="flex"
      justify="space-between"
    >
      <el-button type="primary">
        新增
      </el-button>
      <a href="#">单位任务延期申请</a>
    </el-row>
    <el-row>
      <el-table
        border
        :data="tableData"
        row-key="id"
      />
    </el-row>
  </div>
</template>

<script>
  export default {
    name: "AboutTable",
    data(){
      return {
        tableData: [],
      };
    }
  }
</script>

<style scoped>

</style>
