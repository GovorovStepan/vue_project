<template>
  <div id="app">
    <div class="block">
      <Tree class="tree" />
      <Side />
    </div>
    <img style='position: absolute; top: 185px; right: 33px;' src="https://velesexpert.velespro.ru/cats/1c-cat.png">
    <el-tabs type="card" @tab-click="handleClick">
      <el-tab-pane label="Подбор товара">
        <h3>Подбор товара</h3>
        <SearchProducts />
      </el-tab-pane>
      <el-tab-pane label="Текущие оплаты">
        <h3>Текущие оплаты</h3>
        <Payments />
      </el-tab-pane>
      <el-tab-pane label="Текущий заказ">
        <h3>
          Текущий заказ
          <span style="color: #ddd; font-size: 11px">(отгружен)</span>
        </h3>
        <DealOrder />
      </el-tab-pane>
      <el-tab-pane label="Составной товар">
        <h3>Составной товар</h3>
        <Table2 />
      </el-tab-pane>
      <el-tab-pane label="Поставка">
        <h3>Поставка</h3>
        <Shipment />
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import SearchProducts from "./components/SearchProducts.vue";
import Payments from "./components/Payments.vue";

import Table2 from "./components/Table_2.vue";
import DealOrder from "./components/DealOrder.vue";
import Tree from "./components/Tree.vue";
import Side from "./components/Side_block.vue";
import Shipment from "./components/Shipment.vue";

export default {
  name: "App",
  components: {
    SearchProducts,
    Table2,
    Payments,
    DealOrder,
    Tree,
    Side,
    Shipment,
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 10pt !important;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.12), 0 0 6px rgba(0, 0, 0, 0.04);
  padding: 15px;
  margin-left: auto;
  margin-right: auto;
  max-width: 1160px;
  width: 100%;
  max-height: 870px;
  overflow: auto;
  position: relative;
}

.el-message-box {
  width: auto;
}

.tree {
  width: 30%;
  overflow: auto;
  max-height: 350px;
}
.block {
  border-radius: 4px;
  display: flex;
  padding-bottom: 50px;
}
h3 {
  margin: 40px 0 0;
  padding-bottom: 20px;
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
el-table {
  height: 100%;
}
/* 1с */
/* таблицы */
/* шляпы таблиц */
.el-table thead.is-group th {
  background: #f2f2f2 !important;
}
table .has-gutter tr th {
  background: #f2f2f2;
}
.el-table--border td {
  border-right: none !important;
}
/* table tr th{
      border: 1px solid #ccc;
    } */

table th .cell {
  line-height: 15px !important;
  font-weight: normal;
  font-size: 10pt;
  color: #333;
}
.el-table td,
.el-table th {
  padding: 5px 0 !important;
}

.el-table--enable-row-hover .el-table__body tr:hover > td {
  background-color: white !important;
}

/* knopki */
.el-button--primary {
  background-color: #fde00a !important;
  border-color: #b29d00 !important;
  font-weight: bold !important;
}
.el-button:hover {
  border-color: #b1b1b1 !important;
}
.el-button {
  color: #4b4b4b !important;
  border: 1px solid rgba(0, 0, 0, 0.3);
  border-width: 0 1px;
}
.el-button--button {
  background-color: #fcfcfc;
}
.el-button--button:hover {
  background-color: #fcfcfc !important;
}
/*вкладки*/
.el-tabs__item.is-active {
  color: #333333 !important;
  background-color: white;
  border-bottom: 2px solid #009646 !important;
}
.el-tabs__item:hover {
  color: #333333 !important;
  cursor: pointer;
}
.el-tabs__item {
  background-color: #f2f2f2;
  height: 34px !important;
  line-height: 34px !important;
  font-size: 13px !important;
}
/*progress bar*/
.el-progress-bar__inner {
  background-color: #009646 !important;
}
/*+button in modal window blyat */
.el-input-number__decrease:hover,
.el-input-number__increase:hover {
  color: black !important;
}
.el-input-number__decrease:hover:not(.is-disabled)
  ~ .el-input
  .el-input__inner:not(.is-disabled),
.el-input-number__increase:hover:not(.is-disabled)
  ~ .el-input
  .el-input__inner:not(.is-disabled) {
  /*  border-color: #facc1f!important;
        border: 2px !important; */
  border: 2px solid #facc1f !important;
}
.el-dialog__headerbtn:focus .el-dialog__close,
.el-dialog__headerbtn:hover .el-dialog__close {
  color: black !important;
}
.el-link.el-link--primary {
  color: #1c55ae !important;
}
.el-link.el-link--primary:hover {
  color: #1c55ae !important;
}
/*search */
.el-input.is-active .el-input__inner,
.el-input__inner:focus {
  border: 2px solid #facc1f !important;
  outline: 0;
}
/*tree*/
.el-tree-node__label {
  padding-left: 6px;
  border-left: 2px solid green;
}
.el-tree-node__content:hover {
  background-color: #f2f2f2 !important;
}
.el-tree-node:focus>.el-tree-node__content {
    background-color: #f2f2f2 !important;
}
/*buttons in table  */
.el-button--mini, .el-button--mini.is-round {
    max-width: 100px;
    min-width: 100px;
    padding: 6px 0 !important;
}
.el-button:focus, .el-button:hover {
    background-color: inherit !important;
}
</style>

