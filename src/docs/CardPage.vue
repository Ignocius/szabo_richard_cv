<template>
  <section class="row d-flex justify-content-around">
    <card v-for="(card, index) in dynamicCards" :key="index" :className="setSizeByType(card.type)">
      <card-header v-if="card.header" :className="'d-flex justify-content-center align-items-center'">
        <div class="card-head d-flex justify-content-center align-items-center flex-column"> 
          <i :class="'z-depth-2 card-head-title d-flex justify-content-center align-items-center rounded-circle blue lighten-1 fa ' + card.header.icon" aria-hidden="true"></i>
          <h5>{{card.header.title}}</h5>
        </div>
      </card-header>
      <card-body>
        <section class="d-flex flex-wrap" v-if="card.type !== 'general'">
          <div class="col-12 col-md-6 col-sm-6 d-flex flex-column justify-content-between">
          <section v-for="(personalInfo, index) in card.personalData" v-if="card.personalData" :key="index" class="d-flex info-section">
            <div v-for="(info, key) in personalInfo" :key="key" class="d-flex info-container justify-content-between">
              <span class="info">{{toCamelCase(key)}}: </span>
              <p>{{info}}</p>
            </div>
          </section>
        </div>
        <aside class="col-12 col-md-6 col-sm-6 mt-sm-2" v-if="card.aboutMe">
          <h4>Hi! I am Richard Szabo</h4>
          <p>
            {{card.aboutMe.aboutMeText}}
          </p>
          <div v-for="(btn, index) in card.aboutMe.aboutMeFunction" v-if="aboutMe.aboutMeFunction" :key="index">
            <a v-if="!btn.funct" target="_blank" :href="btn.href" class="funct-btn btn btn-rounded waves-effect waves-light">
              {{btn.title}}
            </a>
          </div>
        </aside>
        </section>
        <section v-if="card.type === 'general'">
          <div v-for="(skill, index) in card.skillSet" :key="index"> 
            <p class="skill-title">{{skill.title}}</p>
            <div class="progress">
              <div class="progress-bar" role="progressbar" :style="`width: ${skill.knowladge}`" :aria-valuenow="skill.knowladge" aria-valuemin="0" aria-valuemax="100"></div>
            </div>
          </div>
        </section>
        <section v-if="card.type === 'experience'" class="col-12 d-flex flex-wrap">
          <div class="col-md-7">
            <div v-for="(exp, index) in card.experience" :key="index" class="border-right d-flex justify-content-between"> 
              <p class="exp-title text-left">{{exp.date}}</p>
              <p class="exp-title text-right">{{exp.work}} <i class="fa fa-check-square-o check" aria-hidden="true"></i></p>
            </div>
          </div>
          <div class="col-md-4 summarry">
            <p>
              {{card.summarry}}
            </p>
          </div>
        </section>
      </card-body>
    </card>
  </section>
</template>

<script>
import card from '@/components/Card';
import cardHeader from '@/components/CardHeader';
import cardBody from '@/components/CardBody';

export default {
  name: 'CardPage',
  props: {
    dynamicCards: {
      type: Array,
      default: (() => [])
    }
  },
  data() {
    return {
    };
  },
  methods: {
    setSizeByType (type) {
      return type === 'general' ?  'col-12 col-lg-5 col-sm-12 mt-5' : 'col-12 col-lg-10 col-sm-12 mt-5 mx-auto' ;
    },
    toCamelCase (string) {
      return string.substring(0, 1).toUpperCase() + string.substring(1);
    },
  },
  components: {
    'Card': card,
    'CardHeader': cardHeader,
    'CardBody': cardBody
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .info-section {
      border-bottom: 1px dashed rgba(0, 0, 0, 0.2);
    }
    .info-section:last-child {
      border: transparent
    }
    .info-container {
      width: 100%;
      padding: 5px 0;
    }
    .info-container p {
      margin: 0;
      min-width: 50%;
    }
    .info-container .info {
      height: 25px;
    }

    .card-header {
      background: transparent
    }

    .card-head-title {
      color: white;
      font-size: 2em;
      width: 2em;
      height: 2em;
      margin-top: -35px;
    }

    .skill-title {
      margin: 0;
      padding: 5px 0;
    }

    .funct-btn {
      background-color: #2196f3 !important;
    }

    .summarry {
      width: 100%;
      border-left: 2px solid #007bff;
    }

    .check::before {
      color: #007bff
    }
</style>
