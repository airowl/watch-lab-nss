<template>
  <section id="hero-slider" >
    
    <div class="carousel">

      <div class="content" :class="i === indexActive ? 'is-active' : ''" v-for="(e, i) in sliderData" :key='i' :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }">
        <div class="overlay dark"></div>
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
          image: 'hero-slider.jpg',
        },
        {
          text: 'The Path to Success with Watchlablab',
          image: 'gallery-1.jpg',
        },
        {
          text: 'The Path to Success with Watchlablablab',
          image: 'gallery-2.jpg',
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
  width: 100vw;
  height: 40vh;
  @include position(relative);
  z-index: 3;
  color: $white;
  

  @include breakpoint-up(large){
    height: 14rem;
    width: 19.5rem;
    @include position(absolute, $bottom: 0, $right: 5rem);
  };

  div.carousel{
    height: 100%;
    overflow: hidden;
    @include d-flex(row, center, center);
    @include position(relative);

    div.content{
      padding: 1.9rem 1.13rem 1.13rem;
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      opacity: 0;
      @include position(absolute, $top: 0, $left: 19.5rem, $bottom: 0, $right: 0);
      @include transition;
  
      &.is-active{
        opacity: 1;
        left: 0;
      }
  
    }
  }


  div.next, div.previous{
    @include position(absolute, $bottom: 2rem);
    z-index: 3;
    cursor: pointer;
    @include d-flex(row, space-between, center);
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