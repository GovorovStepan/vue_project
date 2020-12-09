<template>
  <el-button type="button" @click="open">Добавить в текущий резерв</el-button>
</template>

<script>
import ModalContent from './Modal_content.vue'
  export default {
    methods: {
      open() {
        this.$msgbox({
        customClass:'modal-container',
          title: 'Формирование нового резерва',
          message: <ModalContent/>,
          confirmButtonText: 'Добавить в текущий резерв',
          beforeClose: (action, instance, done) => {
            if (action === 'confirm') {
              instance.confirmButtonLoading = true;
              instance.confirmButtonText = 'Loading...';
              setTimeout(() => {
                done();
                setTimeout(() => {
                  instance.confirmButtonLoading = false;
                }, 300);
              }, 3000);
            } else {
              done();
            }
          }
        }).then(action => {
          this.$message({
            type: 'info',
            message: 'action: ' + action
          });
        });
      },
      name: 'Modal',
         components: {
            ModalContent}
    }
  }
</script>

<style scoped>
.modal-container{width: auto !important;
width: 1000px;}
</style>
