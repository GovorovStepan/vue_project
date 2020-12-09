<template>
 <el-table
          :data="tableData"
          height="1000"
          style="width: 100%">
          <el-table-column
            type="index"
            :index="indexMethod"
            label="Код товара">
          </el-table-column>
          <el-table-column
            prop="name"
            label="Наименование">
          </el-table-column>
          <el-table-column
            prop="art"
            label="Артикул">
          </el-table-column>
          <el-table-column
            prop=""
            label="Дата оплаты">
          </el-table-column>
          <el-table-column
            prop=""
            label="Сумма оплаты">
          </el-table-column>
          <el-table-column
            prop=""
            label="номер счета">
          </el-table-column>
          <el-table-column
            prop=""
            label="Тип оплаты">
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