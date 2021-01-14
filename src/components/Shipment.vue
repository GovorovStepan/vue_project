<template>
    <div>
        <el-table
                :data="tableData"
                stripe
                border
                style="width: 100%">
            <el-table-column prop="name" label="Наименование" width="130" />
            <el-table-column type="index" label="Код товара" width="100" />

            <el-table-column
                    prop="art"
                    label="Артикул"
                    width="100">
            </el-table-column>
            <el-table-column label="Кол-во" width="260" />
            <el-table-column label="Дата поставки" width="150" />
        </el-table>
    </div>
</template>

<script>
    export default {
        name: 'Shipment',
        data() {
            return {
                tableData: [{
                    name: 'China',
                    art: '100 045 646'
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