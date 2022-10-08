<template>
  <section id="hero">
    <div class="overlay"></div>

    <div class="hero-content">
      <p class="up-b text-center">London collection season</p>
      <h1 class="text-center">New Selection Of <br/> Herny London</h1>
      <p class="sm text-center">An estimable experience in the modern collection house</p>
      <Button text="Discover" url="#" />
    </div>
  </section>
</template>

<script>
import Button from './Button.vue'
export default {
  components: { Button },
  name: 'mainHero',
}
</script>

<style lang='scss' scoped>
section#hero{
  background-image: url('../assets/images/hero.jpg');
  background-position: bottom;
  background-repeat: no-repeat;
  background-size: cover;
  width: 100vw;
  height: 36.5rem;
  position: relative;
  color: $white;

  @include breakpoint-up(x-large){
    height: 45rem;
  };

  div.hero-content{
    position: relative;
    z-index: 3;
    height: 100%;
    width: 100%;
    @include d-flex(column, center, center);

    h1{
      margin-bottom: 35px;
      letter-spacing: 3px;

      @include breakpoint-up(large){
        font-size: 3.5rem;
      };
    }

    p{
      
      &.up-b{
        margin-bottom: 48px;
      }

      &.sm{
        margin-bottom: 45px;
      }
    }
  }
}
</style>