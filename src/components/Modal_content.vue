<template>
<div class='modal-container'>
     <el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="name"
        label="Наименование"
        width="180">
      </el-table-column>
      <el-table-column
        prop="county"
        label="Колличество"
        width="180">
        <el-input-number v-model="num" @change="handleChange" :min="1" :max="10"></el-input-number>
      </el-table-column>
      <el-table-column
        prop="type"
        label="Тип цены"
        width="180">
        <el-select v-model="value" placeholder="Выбрать тип"
          width="150">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
      </el-table-column>
         <!--
      <el-table-column
        prop="btn"
        label="Согласовать стоимость"
        width="220">
        <el-checkbox v-model="checked">Ответственный Пан Пан</el-checkbox>
      </el-table-column>
      -->
    </el-table>
</div>
</template>
<script>
  export default {
    data() {
      return {
        num: 1,
        tableData: [{
            name: 'Код товара, Наименование товара, Арт.: 4444444',
            county: '<el-input-number v-model="num" @change="handleChange" :min="1" :max="10"></el-input-number>'
          },],
          options: [{
          value: 'Option1',
          label: 'Option1'
        },{
          value: 'Option2',
          label: 'Option2'
        } ],
      };
    },
    methods: {
      handleChange(value) {
        console.log(value)
      }
    }
  };

</script>

<style scoped>
.modal-container{ 
    min-width: 600px;
}

</style>