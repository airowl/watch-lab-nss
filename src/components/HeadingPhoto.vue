<template>
  <section id='heading-photo' class="container heading-photo" :class="isRightTitle === true ? 'invert' : ''">
    <div class="content">
      <p class="uppercase text-center">{{preTitle}}</p>
      <h2 class="text-center">{{title}}</h2>
      <p class="text-center">
        {{text}}
      </p>
      <Button text="Discover" url="#" />
    </div>
    <div class="main-image" :style="{ backgroundImage: `url(${require('@/assets/images/' + image)})` }"></div>
  </section>
</template>

<script>
import Button from './Button.vue';

export default {
  name: 'HeadingPhoto',
  props: {
    image: String,
    preTitle: String,
    title: String,
    text: String,
    isRightTitle: Boolean,
  },
  components: {
    Button
  }
}
</script>

<style lang='scss' scoped>
section#heading-photo{
  @include d-flex(column-reverse, center, center);

  @include breakpoint-up(large){
    @include d-flex(row, center, center);

    &.invert{
      @include d-flex(row-reverse, center, center);
    }
  };

  .main-image, .content{
    width: 100%;
    height: 25rem;

    @include breakpoint-up(large){
      width: 50%;
      height: 36rem;
    };
  }

  .content{
    @include d-flex(column, center, center);

    h2{
      margin-bottom: 2rem;
      letter-spacing: 1px;

      @include breakpoint-up(large){
        font-size: 2.5rem;
        margin-bottom: 6rem;
        padding: 0 6rem;
      };
    }

    p{
      
      &:first-of-type{
        margin-bottom: 1rem;
        letter-spacing: 3px;
        font-family: "Montserrat-b", "sans-serif";

        @include breakpoint-up(large){
          margin-bottom: 2.3rem;
        };
      }

      &:last-of-type{
        margin-bottom: 45px;
        font-family: "Miller", "sans-serif";
        color: $text-p;
        line-height: 2;
        font-size: .8rem;
        letter-spacing: 2px;
        padding: 0 1rem;

        @include breakpoint-up(large){
          padding: 0 3.5rem;
          font-size: 1rem;
        };
      }
    }
  }

  .main-image{
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
  }
}
</style>