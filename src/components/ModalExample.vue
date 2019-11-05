<template>
  <div>
    <el-button
      type="primary"
      @click="handleButtonClick"
    >
      点击弹窗
    </el-button>
    <el-dialog
      modal
      show-close
      close-on-press-escape
      close-on-click-modal
      title="自定义弹窗"
      :visible.sync="visiable"
    >
      <el-table :data="ModalData">
        <el-table-column
          property="date"
          label="日期"
          width="150"
        />
        <el-table-column
          property="name"
          label="姓名"
          width="200"
        />
        <el-table-column
          property="address"
          label="地址"
        />
      </el-table>
      <span
        slot="footer"
        class="dialog-footer"
      >
        <el-button @click="visiable = false">取 消</el-button>
        <el-button
          type="primary"
          @click="visiable = false"
        >确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
  export default {
    name: "ModalExample",
    props: {
      ModalData: Array,
    },
    data() {
      return {
        visiable: false,
      };
    },
    methods: {
      handleButtonClick () {
        this.visiable = true;
      }
    }
  }

</script>

<style scoped>

</style>
