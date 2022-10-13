<template>
  <section id='blog-slider' data-aos="fade-up">
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
        <div class="wrapper-image">
          <a :href="e.url" class="image" :class="i === indexActive ? 'is-active' : ''" v-for="(e, i) in sliderData" :key='i'  :style="{ backgroundImage: `url(${require('@/assets/images/' + e.image)})` }">
          </a>
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
              <a :href="e.url">
                <h4>
                  {{e.title}}
                </h4>
              </a>
            </div>
          </div>
          <div class="icons">
            <i class="fa-solid fa-chevron-left fa-2xs" @click="downIndexActive()"></i>
            <i class="fa-solid fa-chevron-right fa-2xs" @click="upIndexActive()"></i>
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
      autoPlay: null,
      sliderData: [
        {
          preTitle: 'press',
          title: 'Most Important Days on Watchlab',
          date: '18 settembre 2015',
          image: 'blog-1.jpg',
          url: '#',
        },
        {
          preTitle: 'top',
          title: 'Title Blog 1',
          date: '12 settembre 2015',
          image: 'blog-2.jpg',
          url: '#',
        },
        {
          preTitle: 'good',
          title: 'Title Blog 2',
          date: '9 ottobre 2015',
          image: 'blog-3.jpg',
          url: '#',
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

<style lang='scss' scoped>
section#blog-slider{
  @include d-flex(column, center, center);
  margin: 1rem 0;

  @include breakpoint-up(large){
    @include d-flex(row, center, center);
    margin: 5.63rem 0;
  };

  .slider, .content{
    width: 100%;

    @include breakpoint-up(large){
      width: 50%;
      height: 36rem;
    };
  }

  .content{
    padding: 0 1rem;
    padding-bottom: 2rem;

    @include breakpoint-up(large){
      padding: 0;
    };
    
    p{
      margin-top: 3rem;

      @include breakpoint-up(large){
        width: 54%;
      };
    }
  }

  .slider{
    @include position(relative);
    background-color: transparent;

    @include breakpoint-up(large){
      height: 36rem;
      background-color: #f8f9f8;
    };

    div.carousel{
      @include d-flex(column, center, center);
      @include transition;

      @include breakpoint-up(large){
        @include position(absolute, $bottom: 2rem, $right: 0);
        @include d-flex(row, center, center);
        height: 25rem;
        width: 50rem;
      };

        div.wrapper-image{
          @include position(relative);
          width: 100vw;
          height: 40vh;
          overflow: hidden;

          @include breakpoint-up(large){
            width: 60%;
            height: 100%;
          };

          a.image{
            @include position(absolute, $top: 0, $left: 100%, $bottom: 0, $right: 0);
            display: inline-block;
            @include default-bg;
            filter: grayscale(100%);
            opacity: 0;
            @include transition;
  
            &.is-active{
              opacity: 1;
              left: 0;
              
              &:hover{
                transform: scale(1.1);
              }
            }

          }
        }
  
        div.description{
          width: 100vw;
          height: 40vh;
          padding-left: 2rem;
          padding-top: 2rem;
          padding-right: 2rem;

          @include breakpoint-up(large){
            width: 40%;
            height: 100%;
            padding-top: 0;
            padding-right: 0;
          };

          div.wrapper-text{
            @include position(relative);
            @include d-flex(row, center, center);
            height: 80%;
            overflow: hidden;

            @include breakpoint-up(large){
              height: 45%;
            };

            div.text{
              @include position(absolute, $top: 0, $left: 100%, $right: 0);
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

              a{
                display: inline-block;
                margin-top: 2.2rem;
                color: $black;

                &:hover{
                  text-decoration: underline;
                }
              }
            }
          }
        }

        div.icons{
          //margin-top: 2.5rem;
          height: 20%;

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
</style>