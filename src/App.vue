<template>
  <!--<img alt="Vue logo" src="./assets/logo.png">
  <h1>History and Patriarcal Season</h1>
  <h2>Temporary Store</h2>
  <h3>Most Important Days on Watchlab</h3>
  <h4>Watch/lab</h4>
  <p>On the other hand, we denounce with righteous indingation and dislike men who are so beguiled and demoralizied by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain trouble</p>
  <ul>
    <li>home</li>
    <li>home</li>
    <li>home</li>
  </ul>
  <Button text="Discover" url='#' />-->
  <Header />
  <Hero />
  <HeadingPhoto 
    image='building-1.jpg'
    preTitle='London collection season'
    title='Temporary Store'
    text='On the other hand, we denounce with righteous indingation and dislike men who are so beguiled and demorialized bt the charms of pleasure of the moment, so blinded by desire'
    :isRightTitle=false
  />
  <HeadingPhoto 
    image='building-2.jpg'
    preTitle='London collection season'
    title='New Selection Of Herny London'
    text='On the other hand, we denounce with righteous indingation and dislike men who are so beguiled and demorialized bt the charms of pleasure of the moment, so blinded by desire'
    :isRightTitle=true
  />
  <Gallery />
</template>

<script>
import Gallery from './components/Gallery.vue';
import Header from './components/Header.vue';
import HeadingPhoto from './components/HeadingPhoto.vue';
import Hero from './components/Hero.vue';

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    Gallery,
    HeadingPhoto,

  }
}
</script>

<style lang="scss">
//@import '@/scss/main.scss';

</style>
