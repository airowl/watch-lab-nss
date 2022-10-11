<template>
  <a href={url} class="btn">
    {{text}}
  </a>
</template>

<script>
export default {
  name: 'mainButton',
  props: {
    text: String,
    url: String
  }
}
</script>

<style lang='scss' scoped>
a.btn{
  width: 13.5625rem;
  height: 2.6875rem;
  border: 1px solid $text-footer;
  color: $text-footer;
  @include d-flex(row, center, center);
  @include transition;

  &:hover{
    color: $white;
    background-color: $text-footer;
  }
}
</style>