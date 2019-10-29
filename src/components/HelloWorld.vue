<template>
  <el-row gutter="20">
    <el-col span="7">
      <TreeNode/>
    </el-col>
    <el-col span="17">
      <FormNode/>
    </el-col>
  </el-row>
</template>

<script>
  /* eslint-disable */
  import TreeNode from './TreeNode.vue';
  import FormNode from './FormNode.vue';
export default {
  name: 'HelloWorld',
  components: {
    TreeNode,
    FormNode,
  },
}
</script>
