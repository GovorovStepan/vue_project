<template>
<el-table
          :data="tableData"
          border
          stripe
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
            label="Колличество остатков товара на складах"
            width="180">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество зарезервированного товара"
            width="180">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество заказанного товара(новая поставка)"
            width="200">
          </el-table-column>
          <el-table-column
            prop=""
            label="Срок поставки для данного товара"
            width="160">
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
          <el-table-column
            prop=""
            label="Томоженный индефикатор"
            width="120">
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