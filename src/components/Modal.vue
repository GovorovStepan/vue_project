<template>
    <div>
        <el-button type="primary" size="small" @click="editOrderVisible = true" icon="el-icon-circle-plus-outline">
            <slot />
        </el-button>
        <el-dialog :visible.sync="editOrderVisible" width="720px">
            <el-table :data="tableData" style="width: 100%" stripe>
                <el-table-column prop="name" label="Наименование" width="250">
                    <div>Код товара: 25164</div>
                    <div>Наименование: Chine</div>
                    <div>Артикул: 100045646</div>
                </el-table-column>
                <el-table-column prop="county" label="Колличество" width="250">
                    <table>
                        <tbody>
                            <tr>
                                <td>СПБ: </td>
                                <td><el-input-number size="mini" v-model="num" :min="1" :max="10" /></td>
                            </tr>
                            <tr>
                                <td>Москва: </td>
                                <td><el-input-number size="mini" v-model="num" :min="1" :max="10" /></td>
                            </tr>
                            <tr>
                                <td>Поставка: </td>
                                <td><el-input-number size="mini" v-model="num" :min="1" :max="10" /></td>
                            </tr>
                        </tbody>
                    </table>
                </el-table-column>
                <el-table-column prop="type" label="Тип цены" width="180">
                    <el-select size='small'  v-model="value" placeholder="Выбрать тип">
                        <el-option :key="item.value" :label="item.label" v-for="item in options" :value="item.value" />
                    </el-select>
                </el-table-column>
            </el-table>

            <div style="margin-top: 20px; text-align: left;">
                Дата окончания брони: <el-date-picker  size='small' type="date" />
            </div>

        </el-dialog>
    </div>

</template>

<script>
    export default {
        methods: {},
        data() {
            return {
                num: 1,
                editOrderVisible: false,
                tableData: [{}],
                options: [{
                    value: 'Закупочная',
                    label: 'Закупочная'
                },{
                    value: 'Обычная',
                    label: 'Обычная'
                },{
                    value: 'Пользовательская',
                    label: 'Пользовательская'
                } ],
            }
        },
        name: 'Modal',
        components: {}
    }
</script>
<style scoped />
