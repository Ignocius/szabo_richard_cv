<template>
  <div class="wrapper">
    <aside class="home-background-logo col-12 img-fluid d-flex justify-content-center align-items-center">
      <div class="home-background-profile mx-auto d-block rounded-circle"></div>
    </aside>
    <h2 class="h2-responsive text-center mt-5">Richard Szabo</h2>
    <h3 class="h3-responsive text-center">Front-end Developer</h3>
    <section class="home-socialm-profiles col-12 d-inline-flex justify-content-center align-items-center">
      <div class="col-12 col-sm-12 col-md-4 d-flex justify-content-around align-items-center">
        <a v-for="logo in logoes" :key="logo.key" target="_blank" :href="logo.url" :class="logoes.key">
        <i :class="' d-flex justify-content-center align-items-center rounded-circle hoverable blue lighten-1 fa ' + logo.html" aria-hidden="true"></i>
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
              email: 'ignocius@gmail.com'
            },
            {
              phone: '+3630 924 52 81'
            }
          ],
          aboutMe: {
            aboutMeText: "At my current company I gained solid knowledge in Jquery, HTML, CSS as a front-end developer. I'm working with PHP and NodeJs backed enviroment. I've also worked with Angular, AngularJs, React, currently I'm integrating VueJs applications to our ecosystem. So I've tasted all the main frameworks, but I could manage without them!",
          }
        },
        {
          type: 'experience',
          header: {
            title: 'Experiences',
            icon: 'fa-calendar-check-o'
          },
          experience: [
            {
              date: '2017 - ',
              work: 'Zip2000 as Front-end Developer'
            },
            {
              date: '2010 - 2016',
              work: 'Szabo Tamas Dental Laboratory as dental-technician'
            },
            {
              date: '2006 - 2010',
              work: 'Dr Savanya Norbert Lawyer as Office assistant'
            },
            {
              date: '2006 - 2007',
              work: 'Martonyi and Kajtar Baker & Mckenzie Law Firm as Office assistant',
            },
          ],
          summarry: 'With many years of work experience in different fields, I was ready for the next stage in my career. I was confident that my skills acquired during the four months of study at Green Fox Academy was enough for my career change, and I was right!',
        },
        {
          type: 'general',
          header: {
            title: 'Professional',
            icon: 'fa-gear'
          },
          skillSet: [
            {
              title: 'HTML / CSS',
              knowladge: '80%',
            }, 
            {
              title: 'Javascript / JQuery',
              knowladge: '80%',
            }, 
            {
              title: 'VueJs',
              knowladge: '60%',
            }, 
            {
              title: 'React',
              knowladge: '40%',
            }, 
            {
              title: 'AngularJs',
              knowladge: '25%',
            }, 
          ]
        },
        {
          type: 'general',
          header: {
            title: 'Personal',
            icon: 'fa-user'
          },
          skillSet: [
            {
              title: 'Communication',
              knowladge: '90%',
            }, 
            {
              title: 'Team Work',
              knowladge: '95%',
            }, 
            {
              title: 'Leadership',
              knowladge: '60%',
            }, 
            {
              title: 'Creativity',
              knowladge: '70%',
            }, 
            {
              title: 'Language',
              knowladge: '80%',
            }, 
          ],
        }, 
      ],
    };
  },
  methods: {
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .wrapper {
    font-family: 'Spectral', serif;
    font-size: 1em;
    min-height: 100vh;
    width: 100vw;
    padding-bottom: 5vh;
    /* Permalink - use to edit and share this gradient: http://colorzilla.com/gradient-editor/#ffffff+0,f3f3f3+50,ededed+51,ffffff+100;White+Gloss+%232 */
    background: -moz-linear-gradient(45deg, rgba(255,255,255,1) 0%, rgba(254,255,252,1) 36%, rgba(246,250,251,1) 49%, rgba(234,244,250,1) 69%, rgba(230,242,250,1) 76%); /* ff3.6+ */
    background: -webkit-gradient(linear, left bottom, right top, color-stop(0%, rgba(255,255,255,1)), color-stop(36%, rgba(254,255,252,1)), color-stop(49%, rgba(246,250,251,1)), color-stop(69%, rgba(234,244,250,1)), color-stop(76%, rgba(230,242,250,1))); /* safari4+,chrome */
    background: -webkit-linear-gradient(45deg, rgba(255,255,255,1) 0%, rgba(254,255,252,1) 36%, rgba(246,250,251,1) 49%, rgba(234,244,250,1) 69%, rgba(230,242,250,1) 76%); /* safari5.1+,chrome10+ */
    background: -o-linear-gradient(45deg, rgba(255,255,255,1) 0%, rgba(254,255,252,1) 36%, rgba(246,250,251,1) 49%, rgba(234,244,250,1) 69%, rgba(230,242,250,1) 76%); /* opera 11.10+ */
    background: -ms-linear-gradient(45deg, rgba(255,255,255,1) 0%, rgba(254,255,252,1) 36%, rgba(246,250,251,1) 49%, rgba(234,244,250,1) 69%, rgba(230,242,250,1) 76%); /* ie10+ */
    background: linear-gradient(45deg, rgba(255,255,255,1) 0%, rgba(202, 202, 202, 0.2) 36%, rgba(129, 132, 134, 0) 49%, rgba(21, 30, 37, 0.07) 69%, rgba(2, 13, 21, 0.09) 76%);
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#E6F2FA', endColorstr='#ffffff',GradientType=1 ); /* ie6-9 */
  }

  .home-background-logo {
    background-image: url('../assets/codes-coding-computer-247791.jpg');
    min-height: 100px;
    height: 150px;
    position: relative;
  }

  .home-background-profile {
    max-height: 250px;
    height: 150px;
    width: 150px;
    position: absolute;
    bottom: 0;
    margin-bottom: -40px;
    background-image: url("../assets/mainprofile.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
  }

  .home-socialm-profiles {
    height: 100px;
  }

  .home-socialm-profiles i {
      color: white;
      height: 2em;
      font-size: 2em;
      text-align: center;
      width: 2em;
  }
 
 @media screen and (max-width: 300px) {
    .wrapper {
        font-size: 1.5em;
    }
}

</style>
