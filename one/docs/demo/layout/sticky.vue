<template>
<article>
  <div class="mock-window">
    <veui-layout style="--dls-layout-header-height: 64px;">
      <veui-header sticky>Header</veui-header>
      <veui-layout>
        <veui-sidebar sticky style="max-height: 320px;">
          <div class="center full">Sidebar</div>
        </veui-sidebar>
        <veui-layout>
          <veui-content>
            <div class="center" style="height: 800px;">Sidebar</div>
          </veui-content>
          <veui-footer sticky style="background: #ccc;">Footer（背景仅为演示）</veui-footer>
        </veui-layout>
      </veui-layout>
    </veui-layout>
  </div>
</article>
</template>

<script>
import { Layout, Header, Footer, Sidebar, Content } from 'veui'

export default {
  components: {
    'veui-layout': Layout,
    'veui-header': Header,
    'veui-footer': Footer,
    'veui-sidebar': Sidebar,
    'veui-content': Content
  },
  data () {
    return {
      mode: 'slim',
      modes: [
        { label: 'slim', value: 'slim' },
        { label: 'hidden', value: 'hidden' }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
.mock-window {
  height: 384px;
  transform: translate(0, 0); // bfc for fixed
  overflow: auto;
  border: 1px solid #eee;

  & > .veui-layout {
    min-width: 860px;
  }
}

.center,
.veui-layout-header,
.veui-layout-footer,
.veui-layout-content {
  display: flex;
  align-items: center;
  justify-content: center;
}

.full {
  height: 100%;
}
</style>
