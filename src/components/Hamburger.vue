<template>
  <div class="hamburger" :class='isOpenHam ? "is-active" : "" ' id="hamburger-1">
    <span class="line"></span>
    <span class="line"></span>
    <span class="line"></span>
  </div>
</template>

<script>
export default {
  name: 'headerHamburger',
  props: {
    isOpenHam: Boolean
  },
}
</script>

<style lang='scss' scoped>
.hamburger .line{
  display: block;
  width: 2.5rem;
  height: .19rem;
  margin: 0.5rem auto;
  background-color: $black;
  @include transition;
}

#hamburger-1.is-active .line:nth-child(2){
  opacity: 0;
}

$size-translate: .69rem;
$size-translate-negative: -.69rem;

#hamburger-1.is-active .line:nth-child(1){
  -webkit-transform: translateY($size-translate) rotate(45deg);
  -ms-transform: translateY($size-translate) rotate(45deg);
  -o-transform: translateY($size-translate) rotate(45deg);
  transform: translateY($size-translate) rotate(45deg);
}

#hamburger-1.is-active .line:nth-child(3){
  -webkit-transform: translateY($size-translate-negative) rotate(-45deg);
  -ms-transform: translateY($size-translate-negative) rotate(-45deg);
  -o-transform: translateY($size-translate-negative) rotate(-45deg);
  transform: translateY($size-translate-negative) rotate(-45deg);
}

</style>