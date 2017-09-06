<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-xs-12 col-sm-5 col-md-5 col-lg-5">
          <div class="cv-section__block--left cv-section__block">
            <div class="cv-section__block-inner cv-section__personal-main">
              <div class="cv-section__personal-main-photo">
                <img src="./assets/photo.jpg" class="img-responsive" alt="">
              </div>
              <div class="cv-block__wrapper-name cv-block__wrapper">
                <h1 class="cv-block-name">willi</h1>
              </div>
              <div class="cv-block__wrapper-position cv-block__wrapper">
                <h4 class="cv-block-position">web developer</h4>
              </div>
              <div class="cv-block__wrapper cv-block__wrapper-phone">
                <h4 class="cv-block-phone">+62 857 2030 8893</h4>
              </div>
              <div class="cv-block__wrapper cv-block__wrapper-address">
                <h4 class="cv-block-address">Kawista no. 3 Cigadung Bandung</h4>
              </div>
              <div class="cv-block__wrapper cv-block__wrapper-email">
                <h4 class="cv-block-email">willi.ilmukomputer@gmail.com</h4>
              </div>
              <div class="cv-block__wrapper cv-block__wrapper-linkedin">
                <h4 class="cv-block-linkedin">https://id.linkedin.com/in/willidev</h4>
              </div>
              <div class="cv-block__wrapper cv-block__wrapper-github">
                <h4 class="cv-block-github">https://github.com/willi-dev</h4>
              </div>
            </div>
            <personal-detail :personal="personal" :personalLoaded="personalLoaded"></personal-detail>
            <education :education="education" :eduLoaded="eduLoaded"></education>
            <skills :skills="skills" :skillLoaded="skillLoaded"></skills>
            <training :training="training" :trainingLoaded="trainingLoaded"></training>
          </div>  
        </div>
        <div class="col-xs-12 col-sm-7 col-md-7 col-lg-7">
          <div class="cv-section__block--right cv-section__block">
            
            <workExperience :work="work" :workLoaded="workLoaded"></workExperience>

            <publication :publication="publication" :publicationLoaded="publicationLoaded"></publication>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Firebase from '../node_modules/firebase';
import PersonalDetail from './components/PersonalDetail';
import Education from './components/Education';
import Skills from './components/Skills';
import Training from './components/Training';
import WorkExperience from './components/WorkExperience';
import Publication from './components/Publication';
import VueSticky from '../node_modules/vue-sticky';

const config = {
  apiKey: 'AIzaSyCTn5KIYAtumc2AL_fCNj_n_CZ02pKAQj4',
  authDomain: 'willi-3de27.firebaseapp.com',
  databaseURL: 'https://willi-3de27.firebaseio.com',
  storageBucket: 'willi-3de27.appspot.com',
  messagingSenderId: '19575266674',
  projectId: 'willi-3de27',
};

const app = Firebase.initializeApp(config);
const db = app.database();
const dataPersonalDetail = db.ref('personal_detail');
const dataEducation = db.ref('education');
const dataSkills = db.ref('skills');
const dataTraining = db.ref('training');
const dataWork = db.ref('work_experience');
const dataPublication = db.ref('publication');

export default {
  name: 'app',
  components: {
    personalDetail: PersonalDetail,
    education: Education,
    skills: Skills,
    training: Training,
    workExperience: WorkExperience,
    publication: Publication,
  },
  firebase: {
    personal: {
      source: dataPersonalDetail,
      readyCallback: function personalReady() {
        this.personalLoaded = true;
      },
    },
    education: {
      source: dataEducation,
      readyCallback: function educationReady() {
        this.eduLoaded = true;
      },
    },
    skills: {
      source: dataSkills,
      readyCallback: function skillsReady() {
        this.skillLoaded = true;
      },
    },
    training: {
      source: dataTraining,
      readyCallback: function trainingReady() {
        this.trainingLoaded = true;
      },
    },
    work: {
      source: dataWork,
      readyCallback: function workReady() {
        this.workLoaded = true;
      },
    },
    publication: {
      source: dataPublication,
      readyCallback: function publicationReady() {
        this.publicationLoaded = true;
      },
    },
  },
  data() {
    return {
      personalLoaded: false,
      eduLoaded: false,
      skillLoaded: false,
      trainingLoaded: false,
      workLoaded: false,
      publicationLoaded: false,
      stickyConfig: {
        zIndex: 100,
        stickyTop: 20,
      },
    };
  },
  directives: {
    sticky: VueSticky,
  },
};
</script>

<style lang="scss">
  // always load
  @import './assets/scss/cv-typography.scss';

  // always load in every component for read variables
  @import './assets/scss/cv-variables.scss';

  .list-item {
    // display: inline-block;
    // margin-right: 10px;
  }
  .list-enter-active, .list-leave-active {
    transition: all 1s;
  }
  .list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
    opacity: 0;
    transform: translateY(0);
  }

  .cv-container__loader{
    position: relative;
    height: 100px;
    width: 100%;
  }
  .v-spinner{
    width: 20%;
    top: 50%;
    left: 50%;
    text-align: center;
    position: absolute;
    transform: translate(-50%, -50%);
  }

  .cv{
    margin-top: 20px;
    margin-bottom: 20px;
    .cv-block-text{
      font-size: 1.6rem;
    }

    &-section__block{
      &--left{
        .cv-section__block-title{
          text-align: right;
          @media screen and (max-width: 767px){
            text-align: left;
          }
        }
      }
      &--right{
        .cv-section__block-title{
          text-align: left;
        }
      }

      &-title{
        font-family: $bebasneue;
        color: $greylight-3;
        border-bottom: 1px dashed $greylight-2;
        padding-bottom: 1rem;
      }
    }
  }
</style>