<template>
  <el-form
    :inline="true"
    label-width="80px"
    label-position="right"
    :model="formInline"
  >
    <el-row class="AboutForm">
      <el-col span="8">
        <el-form-item label="年度">
          <el-date-picker
            v-model="formInline.year"
            type="year"
            placeholder="选择年"
          />
        </el-form-item>
      </el-col>
      <el-col span="8">
        <el-form-item label="质量分类">
          <el-select
            v-model="formInline.select"
            placeholder="请选择"
          >
            <el-option
              v-for="item in select"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            />
          </el-select>
        </el-form-item>
      </el-col>
      <el-col span="8">
        <el-form-item label="状态">
          <el-select
            v-model="formInline.state"
            placeholder="请选择"
          >
            <el-option
              v-for="item in state"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            />
          </el-select>
        </el-form-item>
      </el-col>
      <el-col span="8">
        <el-form-item label="名称">
          <el-input
            v-model="formInline.input"
            placeholder="请输入内容"
          />
        </el-form-item>
      </el-col>
      <el-col span="8">
        <el-button type="primary">查询</el-button>
        <el-button>重置</el-button>
      </el-col>
    </el-row>
  </el-form>
</template>

<script>
  export default {
    name: "AboutForm",
    data() {
      return {
        formInline: {
          year: null,
          select: null,
          state: null,
          input: null,
        },
        select: [{
          value: '1',
          label: '高级',
        }, {
          value: '2',
          label: '中级',
        }],
        state: [
          {
            value: '1',
            label: '状态1',
          },
          {
            value: '2',
            label: '状态2',
          },
        ],
      };
    },
  }
</script>

<style scoped>
.AboutForm {
  margin: 10px 0 0;
}
</style>
