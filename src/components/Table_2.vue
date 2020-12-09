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
            label="Остаток"
            width="80">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество
            зарезервироанного товара"
            width="260">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество заказнного товара"
            width="200">
          </el-table-column>
          <el-table-column
            prop=""
            label="Сроки поставки"
            width="150">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество зарезервированного товара в рамках новой поставки"
            width="310">
          </el-table-column>
          <el-table-column
            prop=""
            label="Тип цены"
            width="150">
            <el-select v-model="value" placeholder="Выбрать тип">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
          </el-table-column>
          <el-table-column label="Убрать из составного товара"
          width="180">
          <div class="flex-center">
            <el-button type="danger" icon="el-icon-delete" circle></el-button>
          </div>
          </el-table-column>
        </el-table>
        <div class="bottom-btn_container">
          <Modal class="bottom_btn"/>
        </div>
</div>
</template>

<script>
 
import Modal from './Modal.vue'

  export default {
    name: 'Table2',
    components: {Modal},
    data() {
      return {
        tableData: [{
          name: 'China',
          art: '1,333,240,000'
        }],
         options: [{
          value: 'Option1',
          label: 'Option1'
        },{
          value: 'Option2',
          label: 'Option2'
        } ],
      }
    }
  }
</script>

<style scoped>
.bottom-btn_container{
  display:flex;
  justify-content: flex-end;
}
.bottom_btn{    
  margin: 20px
}
.flex-center{
  display: flex;
  justify-content: center;
}
</style>