<template>
  <div>
    <ModalExample :ModalData="ModalData" />
  </div>
</template>

<script>
  import ModalExample from '../components/ModalExample';
  export default {
    name: "Model",
    data() {
      return {
        ModalData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }],
      };
    },
    components: {
      ModalExample,
    },
  }
</script>

<style scoped>

</style>
