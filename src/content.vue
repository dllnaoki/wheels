<template>
  <div class="g-content">
    <slot></slot>
  </div>
</template>
<script>
export default {
  name: 'GWContent'
}
</script>
<style lang="scss" scoped>
.g-content{
  flex-grow: 1;
}
</style>