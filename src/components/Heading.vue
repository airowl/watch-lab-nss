<template>
  <section id="heading" data-aos="fade-up">
    <h2>
      History and Patriarcal season
    </h2>
    <div class="text">
      <p class="mer">
        On the other hand, we denounce with righteous indingation and dislike men who are so beguiled and demorialized bt the charms of pleasure of the moment, so blinded by desire
      </p>
      <p class="mer">
        But i must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and i will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No that are extremely painful
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'mainHheading'
}
</script>

<style lang="scss" scoped>
section#heading{
  padding: 2rem 0;

  @include breakpoint-up(large){
    margin-bottom: 5.63rem;
    margin-top: 3.63rem;
    padding: 0;
  };

  h2, p{
    padding: 0 1rem;
    
    @include breakpoint-up(large){
      width: 50%;
    };
  }

  h2{
      margin-bottom: 1rem;

    @include breakpoint-up(large){
      margin-bottom: 4rem;
    };
  }

  div.text{
    
    @include breakpoint-up(large){
      @include d-flex(row, center, start);
    };

    p.mer{
    
      &:first-of-type{
        margin-bottom: 1rem;
      }

      @include breakpoint-up(large){
        margin-bottom: 0;
        padding-right: 3rem;
      };
    }
  }
}

</style>