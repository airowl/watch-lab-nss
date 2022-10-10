<template>
  <section id='blog-slider' class="container">
    <div class="content">
      <h2>
        Press from <br/> Watch Lab Studio
      </h2>
      <p class="mer">
        On the other hand, we denounce with righteous indingation and dislike men who are so beguiled and demorialized bt the charms of pleasure of the moment, so blinded by desire
      </p>
    </div>
    <div class="slider">
      <div class="carousel">
        <div class="carousel-inner">
          <div class="wrapper-image">
            <div class="image" :class="i === indexActive ? 'is-active' : ''" v-for="(e, i) in sliderData" :key='i'  :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }">
            </div>
          </div>
          <div class="description">
            <div class="wrapper-text">
              <div class="text" :class="i === indexActive ? 'is-active' : ''"  v-for="(e, i) in sliderData" :key='i'>
                <p class="up-b">
                  {{e.preTitle}}
                </p>
                <p class="up-b">
                  {{e.date}}
                </p>
                <h4>
                  {{e.title}}
                </h4>
              </div>
            </div>
            <div class="icons">
              <i class="fa-solid fa-chevron-left fa-2xs" @click="downIndexActive()"></i>
              <i class="fa-solid fa-chevron-right fa-2xs" @click="upIndexActive()"></i>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BlogSlider',
  data: () => {
    return {
      indexActive: 0,
      sliderData: [
        {
          preTitle: 'press',
          title: 'Most Important Days on Watchlab',
          date: '18 settembre 2015',
          image: 'hero-slider.jpg',
        },
        {
          preTitle: 'press',
          title: 'Most Important Days',
          date: '18 settembre 2015',
          image: 'gallery-1.jpg',
        },
        {
          preTitle: 'press',
          title: 'Most Important',
          date: '18 settembre 2015',
          image: 'gallery-2.jpg',
        },
      ]
    }
  },
  methods: {
    upIndexActive(){
      if (this.indexActive == this.sliderData.length - 1) {
          this.indexActive = 0;
      } else {
        this.indexActive++;
      }
    },
    downIndexActive(){
      if (this.indexActive == 0) {
          this.indexActive = this.sliderData.length - 1;
      } else {
        this.indexActive--;
      }
    },
    timeSlide(){
      setInterval(() =>{
        this.upIndexActive();
      }, 5000);
    }
  },
  mounted() {
    this.timeSlide();
  }
}
</script>

<style lang='scss' scoped>
section#blog-slider{
  @include d-flex(column-reverse, center, center);

  @include breakpoint-up(large){
    @include d-flex(row, center, center);
  };

  .slider, .content{
    width: 100%;
    height: 25rem;

    @include breakpoint-up(large){
      width: 50%;
      height: 36rem;
    };
  }

  .content{
    
    p{
      margin-top: 3rem;

      @include breakpoint-up(large){
        width: 50%;
      };
    }
  }

  .slider{
    background-color: #f8f9f8;
    position: relative;

    div.carousel{
      width: 50rem;
      height: 28rem;
      position: absolute;
      bottom: 0;
      right: 0;

      div.carousel-inner{
        height: 100%;
        width: 100%;
        @include d-flex(row);
        @include transition;

        div.wrapper-image{
          overflow: hidden;
          width: 60%;
          height: 100%;
          position: relative;

          div.image{
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            position: absolute;
            top: 0;
            left: 5rem;
            right: 0;
            bottom: 0;
            opacity: 0;
            @include transition;
  
            &.is-active{
              opacity: 1;
              left: 0;
            }
          }
        }
  
        div.description{
          width: 40%;
          height: 100%;
          padding-left: 2rem;

          div.wrapper-text{
            position: relative;
            height: 45%;
            @include d-flex(row, center, center);
            overflow: hidden;

            div.text{
              position: absolute;
              top: 0;
              left: 100%;
              right: 0;
              opacity: 0;
              @include transition;
    
              &.is-active{
                left: 0;
                opacity: 1;
              }
    
              p:last-of-type{
                color: $bg-logo;
                margin-top: .5rem;
              }
    
              h4{
                margin-top: 2.2rem;
              }
            }
          }
        }

        div.icons{
          //margin-top: 2.5rem;

          i{
            cursor: pointer;

            &:first-of-type{
              margin-right: 2rem;
            }
          }
        }
      }
    }
  }
}
</style>