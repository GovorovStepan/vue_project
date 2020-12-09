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
            label="Колличество зарезервироанного товара"
            width="200">
          </el-table-column>
          <el-table-column
            prop=""
            label="ФИО менеджера"
            width="150">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество зарезервированного товара  новой поставки"
            width="260">
          </el-table-column>
          <el-table-column
            prop=""
            label="ФИО менеджера новой поставки"
            width="190">
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
            label="Тип товара"
            width="150">
            <el-select v-model="value" placeholder="Выбрать тип">
          <el-option
            v-for="item in goods"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
          </el-table-column>

          <el-table-column
          width="150">
              <el-button type="text" size="small">Изменить кол-во</el-button>
          </el-table-column>
        </el-table>
</template>

<script>
  export default {
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
        goods: [{
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