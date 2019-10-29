<template>
  <el-tree
    default-expand-all
    :data="data"
    ref="tree"
    @node-click="handleTreeNodeClick"
  />
</template>

<script>
  /* eslint-disable */
  export default {
    name: "TreeNode",
    methods: {
      handleTreeNodeClick(arg, node) {
        this.test.$emit('activeId', JSON.stringify({
          id: arg.id,
          label: arg.label,
        }));
        this.node = node;
      },
    },
    data() {
      return {
        data: [
          {
            id: 1,
            label: "一级 1",
            children: [
              {
                id: 4,
                label: "二级 1-1",
                children: [
                  {
                    id: 9,
                    label: "三级 1-1-1"
                  },
                  {
                    id: 10,
                    label: "三级 1-1-2"
                  }
                ]
              },
              {
                id: 2,
                label: "一级 2",
                children: [
                  {
                    id: 5,
                    label: "二级 2-1"
                  },
                  {
                    id: 6,
                    label: "二级 2-2"
                  }
                ]
              },
              {
                id: 3,
                label: "一级 3",
                children: [
                  {
                    id: 7,
                    label: "二级 3-1"
                  },
                  {
                    id: 8,
                    label: "二级 3-2"
                  }
                ]
              }
            ]
          }
        ],
        node: null,
      };
    },
    created() {
      this.test.$on('addTreeData',(res) => {
        const tree = this.$refs.tree;
        const Data = JSON.parse(res);
        const { NewData } = Data;
        if (this.node) {
          tree.insertAfter(NewData, this.node);
        }
      });
    }
  }
</script>
