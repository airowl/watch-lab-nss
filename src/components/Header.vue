<template>
  <header>

    <nav class="navbar">
      <div id="logo">
        <h1>Watch/lab</h1>
      </div>

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
  height: 4rem;
  width: 100vw;
  position: relative;

  @include breakpoint-up(large){
    @include d-flex(row, space-between, center);
  };

  nav.navbar{
    height: 100%;
    width: 100%;
    position: relative;
    z-index: 5;
    background-color: $white;
    @include d-flex(row, space-evenly, center);

    @include breakpoint-up(large){
      @include d-flex(row, start, center);
      width: 20vw;
    };

    div#logo{
      background-color: $bg-logo;
      width: 60vw;
      height: 100%;
      color: $white;
      @include d-flex(row, center, center);
      
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

  div.input-box{
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    z-index: 4;
    width: 100vw;
    height: 100%;
    background-color: $white;
    @include d-flex(row, center, center);
    @include transition;

    @include breakpoint-up(large){
      position: relative;
      top: 0;
      width: 20vw;
      height: 100%;
      z-index: 5;
    };

    &.is-active{
      top: 4rem;
    }

    input#search{
      border: 0;
      border-bottom: 1px solid black;
      width: 6rem;
    }
  }

  ul.menu{
    position: absolute;
    top: -100vh;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100vw;
    height: 100vh;
    z-index: 4;
    background-color: $white;
    font-family: "Montserrat-r", "sans-serif";
    @include d-flex(column, center, center);
    @include transition;

    @include breakpoint-up(large){
      position: relative;
      top: 0;
      width: 60vw;
      height: 100%;
      z-index: 5;
      @include d-flex(row, start, center);
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

}
</style>