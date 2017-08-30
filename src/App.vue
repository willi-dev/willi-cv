<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-xs-12 col-sm-5 col-md-5 col-lg-5">
          <div class="cv-section__block--left cv-section__block">
            
            <div class="cv-section__block-inner cv-section__personal-main">
              <div class="cv-section__personal-main-photo">
                <img src="./assets/willi-photo.jpg" class="img-responsive" alt="">
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

            <personalDetail></personalDetail>

            <education></education>

            <skills></skills>

            <training></training>

          </div>  
        </div>

        <div class="col-xs-12 col-sm-7 col-md-7 col-lg-7">
          <div class="cv-section__block--right cv-section__block">
            
            <workExperience></workExperience>

            <publication></publication>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PersonalDetail from './components/PersonalDetail';
import Education from './components/Education';
import Skills from './components/Skills';
import Training from './components/Training';
import WorkExperience from './components/WorkExperience';
import Publication from './components/Publication';

// const configFirebase = {
//   apiKey: 'AIzaSyCTn5KIYAtumc2AL_fCNj_n_CZ02pKAQj4',
//   authDomain: 'willi-3de27.firebaseapp.com',
//   databaseURL: 'https://willi-3de27.firebaseio.com',
//   storageBucket: 'willi-3de27.appspot.com',
//   messagingSenderId: '19575266674',
//   projectId: 'willi-3de27',
// };

// const app = Firebase.initializeApp(configFirebase);
// const db = app.database();

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
};
</script>

<style lang="scss">
  // always load
  @import './assets/scss/cv-typography.scss';

  // always load in every component for read variables
  @import './assets/scss/cv-variables.scss';

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