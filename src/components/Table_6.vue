<template>
<el-table
          :data="tableData"
          border
          style="width: 100%">
          <el-table-column
            type="index"
            :index="indexMethod"
            label="Код товара"
            width="100">
          </el-table-column>
          <el-table-column
            prop="name"
            label="Наименование"
            width="130">
          </el-table-column>
          <el-table-column
            prop="art"
            label="Артикул"
            width="100">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество заказанного товара"
            width="200">
          </el-table-column>
          <el-table-column
            prop=""
            label="Дата доставки"
            width="150">
          </el-table-column>
        </el-table>
</template>

<script>
  export default {
    data() {
      return {
        tableData: [{
          index: '1',
          name: 'China',
          art: '1,333,240,000'
        }]
      }
    }
  }
</script>