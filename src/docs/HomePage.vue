<template>
  <div>
    <aside class="home-background-logo col-12 img-fluid">
    </aside>
    <img class="home-background-profile mx-auto d-block rounded-circle" src="../assets/mainprofile.jpg">
    <h2 class="h2-responsive text-center">Richard Szabo</h2>
    <h3 class="h3-responsive text-center">Front-end Developer</h3>
    <section class="home-socialm-profiles col-12 d-inline-flex justify-content-center align-items-center">
      <div class="col-3 d-flex justify-content-around align-items-center">
        <a v-for="logo in logoes" :key="logo.key" target="_blank" :href="logo.url" :class="logoes.key">
        <i :class="'d-flex justify-content-center align-items-center rounded-circle hoverable blue lighten-1 fa ' + logo.html" aria-hidden="true"></i>
      </a>
      </div>
    </section>
    <CardPage :dynamicCards="dynamicCards"/>
  </div>
</template>

<script>
import CardPage from './CardPage';

export default {
  components:{
    CardPage,
  },
  data() {
    return {
      logoes:  [
        {
          key: 'linkedin',
          html: 'fa-linkedin-square',
          url: 'https://www.linkedin.com/in/szab%C3%B3-richard-b46891136/'
        },
        {
          key: 'github',
          html: 'fa-github',
          url: 'https://github.com/Ignocius'
        },
        {
          key: 'skype',
          html: 'fa-skype',
          url: 'skype:ignocius?chat'
        },
      ],
      dynamicCards: [
        {
          type: 'aboutMeCArd',
          header: '',
          personalData: [
            {
              age: '30 years',
            },
            {
              addres: "Budapest"
            },
            {
              job: 'Front-end Developer'
            },
            {
              email: 'ignocius@gmailcom'
            },
            {
              phone: '+3630 924 52 81'
            }
          ],
          aboutMe: {
            aboutMeText: "At my current company I gained solid knowledge in Jquery, HTML, CSS as a front-end developer. I'm working with PHP and NodeJs backed enviroment. I've also worked with Angular, AngularJs, React, currently I'am integrating VueJs applications to our ecosystem. So I've tasted all the main frameworks, but I could manage without them!",
            aboutMeFunctiopn: [
              {
                type: 'button'

              }
            ]
          }
        } 
      ]
    };
  },
  methods: {
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .home-background-logo {
    background-image: url('../assets/codes-coding-computer-247791.jpg');
    min-height: 100px;
    height: 35vh;
    position: relative;
    z-index: -1;
  }

  .home-background-profile {
    max-height: 250px;
    height: 150px;
    width: 150px;
    margin-top: -90px;
    z-index: 2;
  }

  .home-socialm-profiles {
    height: 100px;
  }

  .home-socialm-profiles i {
      color: white;
      height: 50px;
      font-size: 2em;
      text-align: center;
      width: 45px
    }
</style>
