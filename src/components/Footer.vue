<template>
  <footer data-aos="fade-up">
    <div class="top-footer">
      <a href="/" id="logo">
        <h1>Watch/lab</h1>
      </a>
      <div class="content">
        <div class="data-company">
          <p>Watch/Lab <span>Innovation brings success</span></p>
          <p>Via Borgogna 5, Milan</p>
          <p>Italy</p>
        </div>
        <ul class="nav1">
          <li v-for="(e,i) in nav1" :key='i'>
            <a :href="e.url" class="footer">{{e.text}}</a>
          </li>
        </ul>
        <ul class="nav2">
          <li v-for="(e,i) in nav2" :key='i'>
            <a :href="e.url" class="footer">{{e.text}}</a>
          </li>
        </ul>
        <ul class="contacts">
          <li v-for="(e,i) in contacts" :key='i'>
            <a :href="e.url" class="footer" :class="e.social ? 'social' : ''">{{e.text}}</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="bottom-footer">
      <p>Copyright Watch/Lab all rights reserved</p>
      <p>website by nssfactory</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'mainFooter',
  data: () => {
    return {
      nav1: [
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
        ],
        nav2: [
          {
            text: 'Press',
            url: '#',
          },
          {
            text: 'Contacts',
            url: '#',
          },
          {
            text: 'Privacy Policy',
            url: '#',
          },
          {
            text: 'Search',
            url: '#',
          },
        ],
        contacts: [
          {
            text: 'T. +39 392 9133937',
            url: '#',
          },
          {
            text: 'M. info@watch-lab.it',
            url: '#',
          },
          {
            text: 'facebook',
            url: '#',
            social: true
          },
          {
            text: 'instagram',
            url: '#',
            social: true
          },
        ],
    }
  }
}
</script>

<style lang="scss" scoped>
footer{

  div.top-footer{
    padding: 4rem 2rem;
    background-color: $bg-footer-top;

    @include breakpoint-up(large){
      padding: 7.38rem 8.88rem 12rem;
    };

    h1{
      margin-bottom: 2.5rem;
      color: $white;
    }

    div.content{
      font-family: "Merriweather", "sans-serif";
      color: $text-footer;

      @include breakpoint-up(large){
        display: grid;
        grid-template-columns: 3fr 1.5fr 1.5fr 3fr;
        gap: 1rem;
        justify-items: start;
      };

      a{
        color: $text-footer;
      }

      div.data-company{

        p{

          &:not(last-child){
            margin-bottom: 1.3rem;
          }

          span{
            margin-left: 1.5rem;
          }
        }
      }

      ul.nav1, ul.nav2, ul.contacts{
        height: 100%;
        margin-top: 2rem;

        @include breakpoint-up(large){
          margin-top: 0;
        };
        

        li{
            font-size: .75rem;
          
          &:not(last-child){
            margin-bottom: 1.3rem;
          }
        }
      }

      ul.contacts{

        a.social{
          font-family: "Montserrat-b", "sans-serif";
          font-size: 0.75rem;
          letter-spacing: 3px;
          text-transform: uppercase !important;
        }
      }
    }
  }

  div.bottom-footer{
    @include d-flex(row, space-between, center);
    padding: 2rem 1rem;
    color: $text-footer;
    background-color: $bg-footer-bottom;

    @include breakpoint-up(large){
      padding: 1.6rem 9rem;
    }
  }
}
</style>