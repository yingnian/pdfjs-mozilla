<template>
  <div class="container">
    <iframe :src="fullPath" width="100%" height="100%"></iframe>
  </div>
</template>

<script>
  export default {
    name: 'pdfMoz',
    props: {
      /** pdf的完整文件路径 */
      url: { type: String, default: '' },
      /** 是否支持打印 */
      print: { type: Boolean, default: false },
      /** 是否支持保存 */
      save: { type: Boolean, default: false },
      /** 是否支持编辑 */
      edit: { type: Boolean, default: false }
    },
    data () {
      return {
        baseUrl: 'pdfjs/web/viewer.html?',
        fullPath: 'pdfjs/web/viewer.html'
      }
    },
    watch: {
      url: {
        immediate: true,
        handler(str) {
          if (str) this.fullPath = this.baseUrl + new URLSearchParams({
            url: str, 
            print: this.print, 
            save: this.save,
            edit: this.edit
          })
        }
      }
    }
  }
</script>

<style scoped lang="scss">
  .container {
    height: 100vh;
  }
</style>
