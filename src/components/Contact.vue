<template>
  <section id="contact" data-aos="fade-up">
    <div class="overlay-light"></div>
    <div class="content">
      <h2 class="text-center">
        Get in Touch
      </h2>
      <p class="up-b text-center">
        Discover more about news. <br/> exclusive events and discount
      </p>
      <form action="" method="post" class="text-center">
        <input type="email" name="email" id="email" placeholder="type your email">
        <button type="submit">ok</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: 'mainContact',
}
</script>

<style lang="scss" scoped>
section#contact{
  @include position(relative);
  @include d-flex(row, center, center);
  height: 15.5rem;
  width: 100%;
  background-image: url('../assets/images/contact.jpg');
  @include default-bg;

  div.content{
    @include position(relative);
    z-index: 5;

    h2{
      color: $white;
      margin-bottom: 1rem;
    }

    p.up-b{
      color: $white;
      margin-bottom: 1.88rem;
    }

    form{
      
      input#email, button{
        font-family: "Merriweather", "sans-serif";
        color: $white;
        border: 1px solid $white;
        background-color: transparent;
        padding: .94rem;
        @include transition;

        &:hover{
          color: $black;
          background-color: $white;
        }
      }

      input#email{
        width: 16.75rem;
        margin-right: 1rem;

        &::placeholder {
          color: $white;
          opacity: 1;
        }

        &:-ms-input-placeholder {
          color: $white;
        }

        &::-ms-input-placeholder {
          color: $white;
        }
      }

      button{
        cursor: pointer;
      }
    }
  }
}
</style>