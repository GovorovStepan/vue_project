<template>
    <div>
        <el-table :data="tableData" border style="width: 100%">
            <el-table-column align="center" label="Код товара" width="100" />
            <el-table-column align="center" prop="name" label="Наименование" width="230" />
            <el-table-column align="center" prop="art" label="Артикул" width="100" />

            <el-table-column label="Общий остаток">
                <el-table-column label="Свободный остаток">
                    <el-table-column align="center" label="Все" />
                    <el-table-column align="center" label="СПБ" />
                    <el-table-column align="center" label="Москва" />
                    <el-table-column align="center" label="Ростов-на-Дону" width="150" />
                </el-table-column>
            </el-table-column>

            <el-table-column align="center" label="Кол-во заказанного товара (поставка)">
                <el-table-column align="center" label="Кол-во зарезевированного товара" width="165">
                    <div style="margin-bottom: 5px">
                        <el-button size="mini" type="button" @click="newOrdersVisible = true">
                            15
                        </el-button>
                    </div>
                    <div>
                        <el-button size="mini" type="button" @click="allOrdersVisible = true">
                            150
                        </el-button>
                    </div>
                </el-table-column>
            </el-table-column>

            <el-table-column label="Сроки поставки" width="135" />
            <!--
            <el-table-column width="120" align="center" label="Все резервы">
                <el-button size="mini" type="button" @click="allOrdersVisible = true">
                    Открыть
                </el-button>
            </el-table-column>
            -->
        </el-table>

        <div style="display: flex; margin-top: 20px;">
            <div style="margin-right: 10px" >
                <Modal class="bottom_btn" >Зарезервировать</Modal>
            </div>
            <el-button type="button" size="small">
                Добавить в составной товар
            </el-button>
        </div>

        <el-dialog title="Поставки товара" :visible.sync="newOrdersVisible" width="25%">
            <el-table border :data="orders" style="width: 100%">
                <el-table-column align="center" prop="deal" label="Сделка">
                    <el-link type="primary">Сделка</el-link>
                </el-table-column>
                <el-table-column align="center" width="135" label="Кол-во" />
                <el-table-column align="center" width="135" label="Дата поставки" />
            </el-table>
        </el-dialog>

        <el-dialog title="Заказы по товару" :visible.sync="allOrdersVisible" width="60%">
            <el-table border :data="orders" style="width: 100%">
                <el-table-column align="center" prop="deal" label="Сделка">
                    <el-link type="primary">Сделка</el-link>
                </el-table-column>
                <el-table-column align="center" label="Кол-во товара">
                    <table>
                        <tbody>
                        <tr>
                            <td>СПБ: </td>
                            <td>20</td>
                        </tr>
                        <tr>
                            <td>Москва: </td>
                            <td>15</td>
                        </tr>
                        <tr>
                            <td>Поставка: </td>
                            <td>8</td>
                        </tr>
                        </tbody>
                    </table>
                </el-table-column>
                <el-table-column prop="manager" align="center" label="Менеджер" />
                <el-table-column align="center" width="135" label="Дата окончания резерва" />
                <el-table-column prop="pay" align="center" label="Оплата" />
            </el-table>
        </el-dialog>
    </div>
</template>

<script>

    import Modal from "./Modal.vue";

    export default {
        components: {Modal},
        data() {
            return {
                allOrdersVisible: false,
                newOrdersVisible: false,
                tableData: [
                    {
                        name: 'China',
                        art: '100 045 646'
                    }
                ],
                orders: [{deal: 'Сделка 1', manager: 'Петров А.В.', pay: 'Да'}, {deal: 'Сделка 2', manager: 'Иванов Б.А.', pay: 'Нет'}]
            }
        }
    }
</script>