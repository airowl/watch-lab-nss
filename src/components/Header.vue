<template>
  <header>

    <nav class="navbar">
      <div id="logo">
        <h4>Watch/lab</h4>
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

    <div class="input-box" :class='isOpenSearch ? "is-active" : "" '>
      <input type="text" name="search" id="search">
      <i class="fa-solid fa-magnifying-glass"></i>
    </div>

    <ul class="menu" :class='isOpenHam ? "is-active" : "" '>
      <li v-for="(e, i) in headerData" :key="i">
        <a href={e.url}>
          {{e.text}}
        </a>
      </li>
    </ul>

    
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
            text: 'About Us',
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
  height: 5rem;
  width: 100vw;
  position: relative;

  nav.navbar{
    height: 100%;
    width: 100%;
    position: relative;
    z-index: 5;
    background-color: $white;
    @include d-flex(row, space-evenly, center);

    div#logo{
      text-transform: uppercase;
      background-color: $bg-logo;
      width: 60vw;
      height: 100%;
      color: $white;
      @include d-flex(row, center, center);
    }

    div.collapse{
      @include d-flex(row, space-evenly, center);
      height: 100%;
      width: 40vw;

      .hamburger .line{
        width: 40px;
        height: 3px;
        background-color: $black;
        display: block;
        margin: 8px auto;
        @include transition;
      }

      #hamburger-1.is-active .line:nth-child(2){
        opacity: 0;
      }

      #hamburger-1.is-active .line:nth-child(1){
        -webkit-transform: translateY(11px) rotate(45deg);
        -ms-transform: translateY(11px) rotate(45deg);
        -o-transform: translateY(11px) rotate(45deg);
        transform: translateY(11px) rotate(45deg);
      }

      #hamburger-1.is-active .line:nth-child(3){
        -webkit-transform: translateY(-11px) rotate(-45deg);
        -ms-transform: translateY(-11px) rotate(-45deg);
        -o-transform: translateY(-11px) rotate(-45deg);
        transform: translateY(-11px) rotate(-45deg);
      }
    }

  }

  div.input-box{
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    z-index: 3;
    width: 100vw;
    height: 5rem;
    background-color: $white;
    @include d-flex(row, center, center);
    @include transition;

    &.is-active{
      top: 5rem;
    }

    input#search{
      border: 0;
      border-bottom: 2px solid black;
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
    font-family: "Montserrat-b", "sans-serif";
    @include d-flex(column, center, center);
    @include transition;

    &.is-active{
      top: 0;
    }

    li{
      margin-bottom: 1rem;

      a{
        color: $black;

        @include transition;

        &:hover{
          text-decoration: underline;
        }
      }
    }
  }

}
</style>