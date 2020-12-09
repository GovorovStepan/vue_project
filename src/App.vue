<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <el-tabs type="card" @tab-click="handleClick">
      <el-tab-pane label="Результаты поиска"><h3>Результаты поиска</h3>
          <Table1/>
      </el-tab-pane>
      <el-tab-pane label="Составной товар"><h3>Составной товар</h3>
        <Table2/>
      </el-tab-pane>
      <el-tab-pane label="Текущие оплаты"><h3>Текущие оплаты</h3>
        <Table3/>
      </el-tab-pane>
      <el-tab-pane label="Итоговый заказ (Таблица текущих резервов по сделке)"><h3>Итоговый заказ (Таблица текущих резервов по сделке)</h3>
        <Table4/>
      </el-tab-pane>
      <el-tab-pane label="Карточка сделки"><h3>Карточка сделки</h3>
        <Table5/>
      </el-tab-pane>
      <el-tab-pane label="Текущий заказ"><h3>Текущий заказ</h3>
        <Table6/>
      </el-tab-pane>

    </el-tabs>
  </div>
</template>

<script>
import Table1 from './components/Table_1.vue'
import Table2 from './components/Table_2.vue'
import Table3 from './components/Table_3.vue'
import Table4 from './components/Table_4.vue'
import Table5 from './components/Table_5.vue'
import Table6 from './components/Table_6.vue'

export default {
  name: 'App',
  components: {
    Table1,
    Table2,
    Table3,
    Table4,
    Table5,
    Table6
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  margin-left: auto;
  margin-right: auto;
  max-width: 1160px;
  width: 100%;
  max-height: 870px;
}

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

