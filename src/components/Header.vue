<template>
  <header>

    <nav class="navbar">
      <div id="logo">
        <h1>Watch/lab</h1>
      </div>

      <div class="collapse">
        <i class="fa-solid fa-magnifying-glass fa-2xl" @click="setIsOpenSearch()"></i>

        <div class="hamburger" :class='isOpenHam ? "is-active" : "" ' id="hamburger-1" @click="setIsOpenHam()">
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
        </div>
      </div>

    </nav>

    <ul class="menu" :class='isOpenHam ? "is-active" : "" '>
      <li v-for="(e, i) in headerData" :key="i">
        <a :href="e.url">
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

export default {
  name: 'mainHeader',
  props: {
    text: String
  },
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
      text-transform: uppercase;
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

      .hamburger .line{
        width: 2.5rem;
        height: .19rem;
        background-color: $black;
        display: block;
        margin: 0.5rem auto;
        @include transition;
      }

      #hamburger-1.is-active .line:nth-child(2){
        opacity: 0;
      }

      $size-translate: .69rem;

      #hamburger-1.is-active .line:nth-child(1){
        -webkit-transform: translateY($size-translate) rotate(45deg);
        -ms-transform: translateY($size-translate) rotate(45deg);
        -o-transform: translateY($size-translate) rotate(45deg);
        transform: translateY($size-translate) rotate(45deg);
      }

      #hamburger-1.is-active .line:nth-child(3){
        -webkit-transform: translateY($size-translate) rotate(-45deg);
        -ms-transform: translateY($size-translate) rotate(-45deg);
        -o-transform: translateY($size-translate) rotate(-45deg);
        transform: translateY($size-translate) rotate(-45deg);
      }
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

      a{
        color: $black;
        @include transition;
        letter-spacing: 1px;

        &:hover{
          text-decoration: underline;
        }
      }

    }
  }

}
</style>