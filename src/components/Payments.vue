<template>
    <div>
        <el-progress :percentage="50" />
        <el-table :data="tableData" border style="width: 100%" stripe>
            <el-table-column prop="payDate" label="Дата оплаты" width="110" />
            <el-table-column prop="sum" label="Сумма оплаты" width="130" />
            <el-table-column label="Полная/Частичная" width="160" />
            <el-table-column prop="payNumber" label="Номер счета" />
        </el-table>

        <div class="bottom-container">
            <h4>Документы:</h4>
            <div>
                <el-button class='bottom_btn' type="button" size="small">Торг12</el-button>
                <el-button class='bottom_btn' type="button" size="small">СФ</el-button>
                <el-button class='bottom_btn' type="button" size="small">УПД</el-button>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    data() {
      return {
        tableData: [{
            payDate: '11.12.20',
            sum: '50000',
            payNumber: 'K002458'
        }]
      }
    }
  }
</script>



<style scoped>
    h4{
        padding-top: 10px;
    }
    .bottom-container{
        display:flex;
        justify-content: flex-start;
    }
    .bottom_btn{
        margin: 20px
    }
</style>