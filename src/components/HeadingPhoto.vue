<template>
  <section data-aos="fade-up" id='heading-photo' :class="isRightTitle === true ? 'invert' : ''">
    <div class="content">
      <p class="up-b text-center">{{preTitle}}</p>
      <h3 class="text-center">{{title}}</h3>
      <p class="mer text-center">
        {{text}}
      </p>
      <Button text="View" url="#" />
    </div>
    <a class="main-image" :href="url">
      <div class="image" :style="{ backgroundImage: `url(${require('@/assets/images/' + image)})` }"></div>
    </a>
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
    url: String
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

  a.main-image, .content{
    width: 100vw;

    @include breakpoint-up(large){
      width: 50%;
      height: 36rem;
    };
  }

  .content{
    @include d-flex(column, start, center);
    margin: 2rem 0;
    
    
    @include breakpoint-up(large){
      margin: 0;
      padding-top: 6.88rem;
    };

    h3{
      margin-bottom: 2rem;

      @include breakpoint-up(large){
        margin-bottom: 3.5rem;
        padding: 0 7rem;
      };
    }

    p{
      
      &.up-b{
        margin-bottom: 1rem;

        @include breakpoint-up(large){
          margin-bottom: 1.5rem;
        };
      }

      &.mer{
        margin-bottom: 2.4rem;
        padding: 0 1rem;

        @include breakpoint-up(large){
          padding: 0 3.5rem;
        };
      }
    }
  }

  a.main-image{
    display: inline-block;
    overflow: hidden;
    height: 40vh;

    @include breakpoint-up(large){
      height: 36rem;
    };

    .image{
      width: 100%;
      height: 100%;
      @include default-bg;
      @include transition;

      &:hover{
        transform: scale(1.1);
      }
    }
  }
}
</style>