<template>
    <div id="app">
        <div class='block'>
            <Tree class="tree"/>
            <Side />
        </div>
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
                <h3>Текущий заказ <span style="color: #ddd;font-size: 11px;">(отгружен)</span></h3>
                <DealOrder />
            </el-tab-pane>
            <el-tab-pane label="Составной товар">
                <h3>Составной товар</h3>
                <Table2/>
            </el-tab-pane>
            <el-tab-pane label="Поставка">
                <h3>Поставка</h3>
                <Shipment />
            </el-tab-pane>
        </el-tabs>
    </div>
</template>

<script>
    import SearchProducts from './components/SearchProducts.vue'
    import Payments from './components/Payments.vue'

    import Table2 from './components/Table_2.vue'
    import DealOrder from './components/DealOrder.vue'
    import Tree from './components/Tree.vue'
    import Side from './components/Side_block.vue'
    import Shipment from "./components/Shipment.vue";

    export default {
        name: 'App',
        components: {
            SearchProducts,
            Table2,
            Payments,
            DealOrder,
            Tree,
            Side,
            Shipment
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
        box-shadow: 0 2px 4px rgba(0, 0, 0, .12), 0 0 6px rgba(0, 0, 0, .04);
        padding: 15px;
        margin-left: auto;
        margin-right: auto;
        max-width: 1160px;
        width: 100%;
        max-height: 870px;
        overflow:auto;
    }

    .el-message-box{
        width: auto;
    }

    .tree{
        width: 30%;
        overflow: auto;
        max-height: 350px;
    }
    .block{
        border-radius: 4px;
        display:flex;
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
    el-table{
        height: 100%;
    }
</style>

