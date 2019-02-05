<script>
  export default {
    name: 'Tabs',
    data () {
      return {
        currentTab: null
      }
    },
    methods: {
      showTab (tabId) {
        const tab = document.getElementById(tabId)
        if (tab) {
          if (this.currentTab) {
            this.currentTab.classList.remove('active')
          }
          tab.classList.add('active')
          this.currentTab = tab
        }
      }
    },
    mounted () {
      this.currentTab = document.getElementById('tab-0')
    },
    render: function (createElement) {
      const buttons = []
      const tabs = []

      // shortcut
      const children = this.$slots.default.filter(item => item.componentOptions.tag === 'tab')

      for (let i = 0; i < children.length; i++) {
        buttons.push(createElement(
          'button',
          {
            attrs: { 'data-target': `tab-${i}` },
            on: {
              click: event => {
                this.showTab(event.target.dataset.target)
              }
            }
          },
          children[i].componentOptions.propsData.title
        ))
        tabs.push(createElement(
          'div',
          {
            class: i === 0 ? 'active tab' : 'tab',
            attrs: { id: `tab-${i}` }
          },
          children[i].componentOptions.children
        ))
      }
      const buttonsContainer = createElement('div', { class: 'buttons' }, buttons)
      const tabsContainer = createElement('div', tabs)

      const root = createElement('div', { class: 'tabs' }, [buttonsContainer, tabsContainer])
      return root
    }
  }
</script>

<style lang="scss" scoped>
  .tab {
    display: none;
  }

  .tab.active {
    display: inherit;
  }
</style>
