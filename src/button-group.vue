<template>
  <div class="g-button-group">
    <slot/>  
  </div>
</template>
<script>
export default {
}
</script>
<style lang="scss" scoped>
  .g-button-group {
    display: inline-flex;
    vertical-align: middle;
    >.g-button {
      border-radius: 0px ;
      border-left: 0px;
      &:not(:first-child):hover {
        box-shadow: -1px 0px 0.5px var(--border-color-hover);
      }
      &:first-child {
        border-left: 1px solid var(--border-color);
        border-top-left-radius: var(--border-radius);
        border-bottom-left-radius: var(--border-radius);
      }
      &:last-child {
        border-top-right-radius: var(--border-radius);
        border-bottom-right-radius: var(--border-radius);

      }
      &:hover {
        border-color:var(--border-color-hover);
        position: relative; 
        // z-index: 1;
        // margin-left: 0;
      }
    }
  }
</style>