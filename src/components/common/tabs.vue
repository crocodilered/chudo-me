
<script>
  import Tab from '@/components/common/tab.vue'

  export default {
    name: 'Tabs',
    computed: {
      items () {
        return this.$slots.default
      }
    },
    render: function (h) {
      const el = h('h1', [
        h('div', {
          class: 'tabs-button'
        }, 'Example Text')
      ])
      console.log(el)
      return el
    }
  }
</script>

<style lang="scss" scoped>
  * {
    color: red;
  }
</style>
