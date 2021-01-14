<template>
    <div>
        <el-table :data="tableData" border style="width: 100%" stripe>

            <el-table-column label="№" width="40" />
            <el-table-column label="Код" width="100" />
            <el-table-column prop="art" label="Артикул" width="100" />


            <el-table-column prop="name" label="Наименование" >
                <el-table-column label="Комментарий для пф" width="200">
                </el-table-column>
            </el-table-column>

            <el-table-column label="Кол-во" width="100" />

            <el-table-column label="Остаток">
                <el-table-column label="Свободный остаток" width="175">

                </el-table-column>
            </el-table-column>

            <el-table-column label="Цена" width="100" />
            <el-table-column label="Цена со скидкой">
                <el-table-column label="Сумма со скидкой" width="150">

                </el-table-column>
            </el-table-column>

            <el-table-column label="Сумма" width="100" />
            <el-table-column label="% НДС" width="100" />
            <el-table-column label="НДС" width="100" />
            <el-table-column label="Всего" width="100" />
            <el-table-column label="Тип цены" width="150">
                <el-select size="small"  v-model="value" placeholder="Выбрать тип">
                    <el-option v-for="item in options"
                            :key="item.value"
                            :label="item.label"
                            :value="item.value">
                    </el-option>
                </el-select>
            </el-table-column>
            <el-table-column width="190">
                <Modal class="bottom_btn">Изменить кол-во</Modal>
            </el-table-column>
            <el-table-column width="145">
                <el-button type="primary" size="small">
                    Освободить
                </el-button>
            </el-table-column>
            <el-table-column width="190">
                <el-button type="primary" size="small">
                    Разукомплектовать
                </el-button>
            </el-table-column>
        </el-table>

        <div style="margin-top: 20px; text-align: left;">
            <el-button type="primary" size="small">Возврат</el-button>
            <el-button type="primary" size="small">Продить все товары</el-button>
        </div>

    </div>

</template>

<script>

    import Modal from "./Modal.vue";

  export default {
      components: {Modal},
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