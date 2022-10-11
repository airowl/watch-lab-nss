<template>
  <Header />
  <Hero />
  <div class="container">
    <Heading />
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
    <BlogSlider />
    <Gallery />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import Footer from './components/Footer.vue';
import Contact from './components/Contact.vue';
import Gallery from './components/Gallery.vue';
import Header from './components/Header.vue';
import Heading from './components/Heading.vue';
import HeadingPhoto from './components/HeadingPhoto.vue';
import Hero from './components/Hero.vue';
import BlogSlider from './components/BlogSlider.vue';

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    Gallery,
    HeadingPhoto,
    Heading,
    Contact,
    Footer,
    BlogSlider,
  }
}
</script>

<style lang="scss">
//@import '@/scss/main.scss';

</style>
