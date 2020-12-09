<template>
        <el-autocomplete style="width: 800px; padding-left:15px"
            popper-class="my-autocomplete"
            v-model="state"
            :fetch-suggestions="querySearchAsync"
            placeholder="Начните вводить название товара"
            @select="handleSelect"
            size= "large"
            >
        </el-autocomplete>
</template>

<script>
  export default {
    data() {
      return {
        links: [],
        state: '',
        timeout:  null
      };
    },
    methods: {
      loadAll() {
        return [
          { }
         ];
      },
      querySearchAsync(queryString, cb) {
        var links = this.links;
        var results = queryString ? links.filter(this.createFilter(queryString)) : links;

        clearTimeout(this.timeout);
        this.timeout = setTimeout(() => {
          cb(results);
        }, 3000 * Math.random());
      },
      createFilter(queryString) {
        return (link) => {
          return (link.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0);
        };
      },
      handleSelect(item) {
        console.log(item);
      }
    },
    mounted() {
      this.links = this.loadAll();
    }
  };
</script>



<style scoped>
  
</style>