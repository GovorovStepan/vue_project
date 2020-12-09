<template>
  <el-tabs type="card" @tab-click="handleClick">
    <el-tab-pane label="Результаты поиска"><h3>Результаты поиска</h3>
        <el-table
          :data="tableData_1"
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
            label="Остаток">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество зарезервироанного товара">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество заказнного товара">
          </el-table-column>
          <el-table-column
            prop=""
            label="Сроки поставки">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество зарезервированного товара в рамках новой поставки">
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
          <el-table-column>
              <el-button type="button" size="small">Зарезервировать</el-button>
          </el-table-column>
          <el-table-column>
            <el-button type="button" size="small">Добавить в составной товар</el-button>
          </el-table-column>
        </el-table>
    </el-tab-pane>
    <el-tab-pane label="Составной товар"><h3>Составной товар</h3>
      <el-table
          :data="tableData_2"
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
            label="Остаток">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество зарезервироанного товара">
          </el-table-column>
          <el-table-column
            prop=""
            label="Колличество заказнного товара">
          </el-table-column>
          <el-table-column
            prop=""
            label="Сроки поставки">
          </el-table-column>
          <el-table-column
            prop=""
            label="Количество зарезервированного товара в рамках новой поставки">
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
          <el-table-column label="Убрать из составного товара">
              <el-button type="danger" icon="el-icon-delete" circle></el-button>
          </el-table-column>
        </el-table>
    </el-tab-pane>
    <el-tab-pane label="Текущие оплаты"><h3>Текущие оплаты</h3>
      <el-table
          :data="tableData_3"
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
    </el-tab-pane>
    <el-tab-pane label="Итоговый заказ (Таблица текущих резервов по сделке)"><h3>Итоговый заказ (Таблица текущих резервов по сделке)</h3>
      <el-table
          :data="tableData_4"
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
    </el-tab-pane>
  </el-tabs>
</template>
<script>
  export default {
    data() {
      return {
        activeName: 'first',
        tableData_1: [{
          index: '1',
          name: 'China',
          art: '1,333,240,000'
        }],
        tableData_2: [{
          index: '1',
          name: 'China',
          art: '1,333,240,000'
        }],
        tableData_3: [{
          index: '1',
          name: 'China',
          art: '1,333,240,000'
        }],
        tableData_4: [{
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
      };
      
    },
    methods: {
      handleClick(tab, event) {
        console.log(tab, event);
      }
    }
  };


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
