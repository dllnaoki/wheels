<template>
  <div class="row" :style="rowStyle" :class="rowClass">
    <slot></slot>
  </div>
</template>
<script>
  export default {
    name: 'GWRow',
    props: {
      gutter: {
        type: [Number, String]
      },
      align: {
        type: String,
        validator (value) {
          return ['left', 'right', 'center'].includes(value)
        }
      }
    },
    computed: {
      rowStyle () {
        let {gutter} = this
        return {marginLeft: -gutter / 2 + 'px', marginRight: -gutter / 2 + 'px'}
      },
      rowClass () {
        let {align} = this
        return [align && `align-${align}`]
      }
    },
    mounted () {
      this.$children.forEach((vm) => {
        // 把间隙传给子节点
        vm.gutter = this.gutter
      })
    }
  }
</script>
<style scoped lang="scss">
  .row{
    display: flex;
    flex-wrap: wrap;
    // border: 1px solid pink;
    &.align-left {
      justify-content: flex-start;
    }
    &.align-right {
      justify-content: flex-end;
    }
    &.align-center {
      justify-content: center;
    }
  }
</style>