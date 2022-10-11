<template>
  <section id="hero">
    <div class="wrapper">
      <div class="overlay"></div>

      <div class="hero-content">
        <p class="up-b text-center">London collection season</p>
        <h2 class="text-center">New Selection Of <br/> Herny London</h2>
        <p class="sm text-center">An estimable experience in the modern collection house</p>
        <Button text="Discover" url="#" />
      </div>
    </div>

    <HeroSlider />

  </section>
</template>

<script>
import Button from './Button.vue';
import HeroSlider from './HeroSlider.vue';

export default {
  components: { 
    Button ,
    HeroSlider,
    },
  name: 'mainHero',
}
</script>

<style lang='scss' scoped>
section#hero{
  width: 100vw;
  position: relative;
  
  div.wrapper{
    background-image: url('../assets/images/hero.jpg');
    background-position: bottom;
    background-repeat: no-repeat;
    background-size: cover;
    width: 100%;
    height: 36.5rem;
    color: $white;

    @include breakpoint-up(x-large){
      height: 40rem;
    };

  }

  div.hero-content{
    position: relative;
    z-index: 3;
    height: 100%;
    width: 100%;
    @include d-flex(column, center, center);

    h2{
      margin-bottom: 2.19rem; // 35px
      color: $white;

      @include breakpoint-up(large){
        font-size: 3.5rem;
      };
    }

    p{
      
      &.up-b{
        margin-bottom: 3rem; //48px
      }

      &.sm{
        margin-bottom: 2.81rem; // 45px
      }
    }
  }
}
</style>