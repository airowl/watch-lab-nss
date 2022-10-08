<template>
  <section id="gallery" class="container">
    <div class="main-image">
      <div class="overlay"></div>
      <div class="content">
        <p class="up-b text-center">Instagram</p>
        <h1 class="text-center">Discover <br/> Watch Lab</h1>
      </div>
    </div>
    <div class="gallery-image">
      <div class="image" v-for="(e, i) in galleryData" :key='i' :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }"></div>
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

  @include breakpoint-up(large){
    @include d-flex(row, center, center);
  };

  .main-image, .gallery-image{
    width: 100%;
    height: 25rem;

    @include breakpoint-up(large){
      width: 50%;
      height: 36rem;
    };
  }

  .main-image{
    background-image: url('../assets/images/gallery-1.jpg');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;

    .content{
      color: $white;
      position: relative;
      z-index: 5;
      width: 100%;
      height: 100%;

      h1{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
      }

      p{
        position: absolute;
        top: 8rem;
        left: 50%;
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
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }
  }
}
</style>