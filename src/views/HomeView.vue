<template>
  <div>
    <button @click="test(1)">测试1</button>
    <button @click="test(2)">测试2</button>
    <div class="home">
      <pdfMoz :url="pdfUrl"></pdfMoz>
    </div>

  </div>
</template>

<script>
import pdfMoz from '../components/pdfMoz.vue'
export default {
  name: 'HomeView',
  components: { pdfMoz },
  data() {
    return {
      pdfUrl: ''
    }
  },
  methods: {
    test(type) {
      this.pdfUrl = type === 1 ? 'http://120.76.44.219:8071/api/profile/Ledger_LJ/2023-02/xls/1688043544958.pdf' : 'http://120.76.44.219:8071/api/profile/Ledger_LJ/2023-05/xls/1688043592237.pdf'
    }
  }
}
</script>
<style lang="scss" scoped>
.home{
  width: 1000px;
}
</style>