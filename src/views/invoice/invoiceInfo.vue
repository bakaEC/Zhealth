<template>
  <div>
    <h1>发票信息</h1>
    <div v-html="invoiceData"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      invoiceData: ''
    };
  },
  mounted() {
    // 在组件挂载后，使用fetch或axios等方式获取数据
    fetch('http://127.0.0.1:5000')
      .then(response => response.text())
      .then(data => {
        // 将获取到的数据存储在invoiceData中，以便在模板中渲染
        this.invoiceData = data;
      })
      .catch(error => {
        console.error('发生错误:', error);
      });
  }
};
</script>
