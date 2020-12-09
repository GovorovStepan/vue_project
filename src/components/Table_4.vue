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
            label="Колличество зарезервироанного товара">
          </el-table-column>
          <el-table-column
            prop=""
            label="ФИО менеджера">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество зарезервированного товара  новой поставки">
          </el-table-column>
          <el-table-column
            prop=""
            label="ФИО менеджера новой поставки">
          </el-table-column>
          <el-table-column
            prop=""
            label="Тип цены">
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
            label="Тип товара">
            <el-select v-model="value" placeholder="Выбрать тип">
          <el-option
            v-for="item in goods"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
          </el-table-column>

          <el-table-column>
              <el-button type="text" size="small">Изменить кол-во</el-button>
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