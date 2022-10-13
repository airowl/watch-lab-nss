<template>
  <section id="hero-slider" >
    
    <div class="carousel">

      <div class="content" :class="i === indexActive ? 'is-active' : ''" v-for="(e, i) in sliderData" :key='i' :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }">
        <div class="overlay-dark"></div>
        <h5>{{e.text}}</h5>
      </div>
    </div>

    <!--<div class="previous" @click="downIndexActive()">
      <i class="fa-solid fa-chevron-left fa-2xs"></i>
      <p class="up-b">
        previous
      </p>
    </div>-->
    <div class="next" @click="upIndexActive">
      <p class="up-b">
        next
      </p>
      <i class="fa-solid fa-chevron-right fa-2xs"></i>
    </div>

  </section>
</template>

<script>
export default {
  name: 'heroSlider',
  data: () => {
    return {
      indexActive: 0,
      sliderData: [
        {
          text: 'The Path to Success with Watchlab',
          image: 'hero-slider-1.jpg',
        },
        {
          text: 'Title 1',
          image: 'hero-slider-2.jpg',
        },
        {
          text: 'Title 2',
          image: 'hero-slider-3.jpg',
        },
      ]
    }
  },
  methods: {
    upIndexActive(){
      this.stopTimeSlide();
      if (this.indexActive == this.sliderData.length - 1) {
          this.indexActive = 0;
      } else {
        this.indexActive++;
      }
      this.timeSlide();
    },
    downIndexActive(){
      this.stopTimeSlide();
      if (this.indexActive == 0) {
          this.indexActive = this.sliderData.length - 1;
      } else {
        this.indexActive--;
      }
      this.timeSlide();
    },
    timeSlide(){
      this.autoPlay = setInterval(() =>{
        this.upIndexActive();
      }, 5000);
    },
    stopTimeSlide(){
      clearInterval(this.autoPlay);
      this.autoPlay = null;
    }
  },
  mounted() {
    this.timeSlide();
  }
}
</script>

<style lang="scss" scoped>
section#hero-slider{
  @include position(relative);
  z-index: 3;
  width: 100vw;
  height: 40vh;
  color: $white;
  

  @include breakpoint-up(large){
    @include position(absolute, $bottom: 0, $right: 5rem);
    height: 14rem;
    width: 19.5rem;
  };

  @include breakpoint-up(xx-large){
    @include position(absolute, $bottom: 0, $right: 5rem);
    height: 18rem;
    width: 23.5rem;
  };

  div.carousel{
    @include position(relative);
    @include d-flex(row, center, center);
    height: 100%;
    overflow: hidden;

    div.content{
      @include position(absolute, $top: 0, $left: 19.5rem, $bottom: 0, $right: 0);
      @include default-bg;
      padding: 1.9rem 1.13rem 1.13rem;
      opacity: 0;
      @include transition;
  
      &.is-active{
        left: 0;
        opacity: 1;
      }
  
    }
  }


  div.next, div.previous{
    @include position(absolute, $bottom: 2rem);
    z-index: 3;
    @include d-flex(row, space-between, center);
    cursor: pointer;
  }

  div.next{
    right: 2rem;

    i{
      margin-left: 1rem;
    }
  }

  //div.previous{
  //  left: 2rem;

  //  i{
  //    margin-right: 1rem;
  //  }
  //}
}
</style>