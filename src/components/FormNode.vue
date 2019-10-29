<template>
    <el-row gutter="20" type="flex" justify="center">
        <el-form ref="form" :model="form" label-width="80px">
            <el-form-item label="节点名称">
                <el-input v-model="form.name"></el-input>
            </el-form-item>
            <el-form-item>
                <el-button type="primary" @click="onCreate">立即创建</el-button>
            </el-form-item>
        </el-form>
    </el-row>
</template>

<script>
    /* eslint-disable */
  export default {
      name: "FormNode",
      data() {
        return {
            activeData: {},
            form: {
                name: '',
            },
        }
      },
      created(){
          this.test.$on('activeId',(res) => {
              const Data = JSON.parse(res);
              this.activeData = Data;
          });
      },
      methods: {
          onCreate: function() {
              if (Object.keys(this.activeData).length) {
                  if (this.form.name === '') {
                      this.$message.error('请输入节点名称！');
                      return;
                  }
                const NewData = {
                    id: parseInt(this.activeData.maxId) + 1,
                    label: this.form.name,
                };
                  const OldData = this.activeData;
                  this.test.$emit('addTreeData', JSON.stringify({NewData, OldData}));
              } else {
                  this.$message.error('请点击左侧某一树节点后再添加节点！');
                  return;
              }
          },
      },
  }
</script>

<style scoped>

</style>
