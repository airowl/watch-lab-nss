<template>
  <section id="gallery">
    <div class="main-image" :class="i > 0 ? 'hidden' : ''" v-for="(e, i) in galleryData" :key='i' :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }">
      <div class="overlay dark"></div>
      <div class="content">
        <p class="up-b text-center">Instagram</p>
        <h2 class="text-center">Discover <br/> Watch Lab</h2>
      </div>
    </div>
    <div class="gallery-image">
      <div class="image" :class="i <= 0 ? 'hidden' : ''" v-for="(e, i) in galleryData" :key='i' :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }"></div>
    </div>
  </section>
</template>

<script>

export default {
  name: 'mainGallery',
  data: () => {
    return {
      galleryData: [
        {
          image: 'gallery-1.jpg',
        },
        {
          image: 'gallery-2.jpg',
        },
        {
          image: 'gallery-3.jpg',
        },
        {
          image: 'gallery-4.jpg',
        },
        {
          image: 'gallery-5.jpg',
        },
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
section#gallery{
  margin-bottom: 3.13rem;

  @include breakpoint-up(large){
    @include d-flex(row, center, center);
  };

  .main-image, .gallery-image{
    width: 100vw;
    height: 40vh;

    @include breakpoint-up(large){
      width: 50%;
      height: 36rem;
    };
  }

  .main-image{
    @include default-bg;
    @include position(relative);

    &.hidden{
      display: none;
    }

    .content{
      color: $white;
      @include position(relative);
      z-index: 5;
      width: 100%;
      height: 100%;

      h2{
        @include position(absolute, $top: 50%, $left: 50%);
        transform: translate(-50%, -50%);
        color: $white;
      }

      p{
        @include position(absolute, $top: 5rem, $left: 50%);
        transform: translate(-50%, -50%);

        @include breakpoint-up(large){
          top: 10rem;
        };
      }
    }
  }

  .gallery-image{
    @include d-flex(row, start, center);
    flex-wrap: wrap;

    .image{
      width: 50%;
      height: 50%;
      @include default-bg;

      &.hidden{
        display: none;
      }
    }
  }
}
</style>