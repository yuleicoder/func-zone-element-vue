<template>
  <div class="app-wrapper">
    <div class="main-container">
      <head-navbar />
      <app-main />
    </div>
  </div>
</template>

<script>
import { HeadNavbar, AppMain } from './components'
import ResizeMixin from './mixin/ResizeHandler'

export default {
  name: 'Head',
  components: {
    HeadNavbar,
    AppMain
  },
  mixins: [ResizeMixin],
  computed: {
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
  @import "~@/styles/mixin.scss";
  @import "~@/styles/variables.scss";

  .main-container {
    margin-left: 0px !important;
  }
  .app-wrapper {
    @include clearfix;
    position: relative;
    height: 100%;
    width: 100%;
  }
  .drawer-bg {
    background: #000;
    opacity: 0.3;
    width: 100%;
    top: 0;
    height: 100%;
    position: absolute;
    z-index: 999;
  }

  .fixed-header {
    position: fixed;
    top: 0;
    right: 0;
    z-index: 9;
    transition: width 0.28s;
  }

  .mobile .fixed-header {
    width: 100%;
  }
</style>
