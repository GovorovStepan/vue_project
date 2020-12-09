<template>
<div>
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
            label="Дата оплаты"
            width="110"
            >
          </el-table-column>
          <el-table-column
            prop=""
            label="Сумма оплаты"
            width="130">
          </el-table-column>
          <el-table-column
            prop=""
            label="Номер счета"
            width="120">
          </el-table-column>
          <el-table-column
            prop=""
            label="Тип оплаты"
            width="120">
          </el-table-column>
        </el-table>
        <div class="bottom-container">
          <h4>Документы:</h4> 
          <div>
            <el-button class='bottom_btn' type="button" size="large">Торг12</el-button>
            <el-button class='bottom_btn' type="button" size="large">СФ</el-button>
            <el-button class='bottom_btn' type="button" size="large">УПД</el-button>
          </div>
        </div>
        </div>
</template>

<script>
  export default {
    data() {
      return {
        tableData: [{
          name: 'China',
          art: '1,333,240,000'
        }]
      }
    }
  }
</script>



<style scoped>
h4{
  padding-top: 10px;
}
.bottom-container{ 
  display:flex;
  justify-content: center;
  }

.bottom_btn{    
  margin: 20px
}
</style>