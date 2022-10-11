<template>
  <section id="contact">
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
  background-image: url('../assets/images/contact.jpg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 15.5rem;
  width: 100%;
  position: relative;
  @include d-flex(row, center, center);

  div.content{
    position: relative;
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
        border: 1px solid $white;
        font-family: "Merriweather", "sans-serif";
        background-color: transparent;
        padding: .94rem;
        color: $white;
      }

      input#email{
        margin-right: 1rem;
        width: 16.75rem;

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
    }
  }
}
</style>