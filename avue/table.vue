<template>
  <basic-container>
    <avue-crud :data="data" :option="option" />
  </basic-container>
</template>

<script>
export default {
  name: 'Avuetable',
  data() {
    return {
      data: [
        {
          name: '张三',
          sex: '男',
          date: '1994-02-23 00:00:00'
        }, {
          name: '李四',
          sex: '女',
          date: '1994-02-23 00:00:00'
        }, {
          name: '王五',
          sex: '女',
          date: '1994-02-23 00:00:00'
        }, {
          name: '赵六',
          sex: '男',
          date: '1994-02-23 00:00:00'
        }
      ],
      option: {
        page: false,
        align: 'center',
        menuAlign: 'center',
        border: true,
        column: [
          {
            label: '姓名',
            prop: 'name',
            search: true
          },
          {
            label: '性别',
            prop: 'sex'
          }, {
            label: '日期',
            prop: 'date',
            type: 'date',
            format: 'yyyy-MM-dd hh:mm:ss',
            valueFormat: 'yyyy-MM-dd hh:mm:ss'
          }
        ]
      }
    }
  }
}

</script>
<style lang='scss' scoped></style>
