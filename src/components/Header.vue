<template>
  <header>

    <nav class="navbar">
      <a href="/" id="logo">
        <h1>Watch/lab</h1>
      </a>

      <div class="collapse">
        <i class="fa-solid fa-magnifying-glass fa-2xl" @click="setIsOpenSearch()"></i>

        <Hamburger 
          :isOpenHam="isOpenHam" 
          @click="setIsOpenHam()"
        />
      </div>

    </nav>

    <ul class="menu" :class='isOpenHam ? "is-active" : "" '>
      <li v-for="(e, i) in headerData" :key="i">
        <a :href="e.url" class="header">
          {{e.text}}
        </a>
      </li>
    </ul>

    <div class="input-box" :class='isOpenSearch ? "is-active" : "" '>
      <input type="text" name="search" id="search">
      <i class="fa-solid fa-magnifying-glass fa-xs"></i>
    </div>

    
  </header>
</template>

<script>
import Hamburger from './Hamburger.vue';

export default {
  components: { Hamburger },
  name: 'mainHeader',
  data: () => {
    return {
        headerData: [
          {
            text: 'About us',
            url: '#',
          },
          {
            text: 'Brand',
            url: '#',
          },
          {
            text: 'Projects',
            url: '#',
          },
          {
            text: 'Magazine',
            url: '#',
          },
          {
            text: 'Press',
            url: '#',
          },
          {
            text: 'Contacts',
            url: '#',
          },
        ],
        isOpenHam: false,
        isOpenSearch: false
    }
  },
  methods: {
    setIsOpenHam(){
      this.isOpenHam = !this.isOpenHam;
    },
    setIsOpenSearch(){
      this.isOpenSearch = !this.isOpenSearch;
    },
  }
}
</script>

<style lang='scss' scoped>
header{
  @include position(relative);
  height: 4rem;
  width: 100vw;

  @include breakpoint-up(large){
    @include d-flex(row, space-between, center);
  };

  nav.navbar{
    @include position(relative);
    z-index: 5;
    @include d-flex(row, space-evenly, center);
    height: 100%;
    width: 100%;
    background-color: $white;

    @include breakpoint-up(large){
      @include d-flex(row, start, center);
      width: 20vw;
    };

    a#logo{
      @include d-flex(row, center, center);
      width: 60vw;
      height: 100%;
      color: $white;
      background-color: $bg-logo;
      
      @include breakpoint-up(large){
        width: 100%;
      };
    }

    div.collapse{
      @include d-flex(row, space-evenly, center);
      height: 100%;
      width: 40vw;

      @include breakpoint-up(large){
        display: none
      };
    }

  }

  ul.menu{
    @include position(absolute, $top: -100vh, $left: 0, $bottom: 0, $right: 0);
    z-index: 4;
    @include d-flex(column, center, center);
    width: 100vw;
    height: 100vh;
    font-family: "Montserrat-r", "sans-serif";
    background-color: $white;
    @include transition;

    @include breakpoint-up(large){
      @include position(relative);
      top: 0;
      z-index: 5;
      @include d-flex(row, start, center);
      width: 60vw;
      height: 100%;
    };

    @include breakpoint-up(xx-large){
      @include d-flex(row, center, center);
    };
    

    &.is-active{
      top: 0;
    }

    li{
      margin-bottom: 2rem;

      @include breakpoint-up(large){
        margin-left: 4rem;
        margin-bottom: 0;
      };

    }
  }

  div.input-box{
    @include position(absolute, $top: 0, $left: 0, $bottom: 0);
    z-index: 4;
    @include d-flex(row, center, center);
    width: 100vw;
    height: 100%;
    background-color: $white;
    @include transition;

    @include breakpoint-up(large){
      @include position(relative);
      top: 0;
      z-index: 5;
      width: 20vw;
      height: 100%;
    };

    &.is-active{
      top: 4rem;
    }

    input#search{
      width: 6rem;
      border: 0;
      border-bottom: 1px solid black;
    }
  }

}
</style>