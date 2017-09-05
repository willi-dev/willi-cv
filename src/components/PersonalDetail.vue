<template>
  <div class="cv-section__block-inner cv-section__personal-detail">
    <h3 class="cv-section__block-title">Personal Detail</h3>
    <div class="cv-container__loader" v-if="personalLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="person in personal" v-bind:key="person" class="list-item">
        <div class="cv-block__wrapper cv-block__wrapper-placedatebirth">
          <h4 class="cv-block-placedatebirth cv-block-text">Place, Date of Birth <span class="value">{{person.placedatebirth}}</span></h4>
        </div>
        <div class="cv-block__wrapper cv-block__wrapper-gender">
          <h4 class="cv-block-gender cv-block-text">Gender <span class="value">{{person.gender}}</span></h4>
        </div>
        <div class="cv-block__wrapper cv-block__wrapper-language">
          <h4 class="cv-block-language cv-block-text">Language <span class="value">{{person.language}}</span></h4>
        </div>
        <div class="cv-block__wrapper cv-block__wrapper-religion">
          <h4 class="cv-block-religion cv-block-text">Religion <span class="value">{{person.religion}}</span></h4>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'personal-detail',
  props: ['personal', 'personalLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/cv-variables.scss';
  .cv{
    &-section__personal-main-photo{
      text-align: right;
      margin-bottom: 1rem;
      img{
        width:60%;
        display: inline;
      }
    }

    &-section__personal-main{
      text-align: right;
      font-family: $raleway;
      .cv-block__wrapper{

      }
      .cv-block-name{
        font-weight: $bold;
        font-size: 10rem;
        line-height: .7;
        margin-top:0;
        margin-bottom:0;
      }
      .cv-block-position{
        font-weight: $light;
        font-size: 6rem;
        // line-height: .5;
        margin-top:0;
        margin-bottom:0;
      }
      .cv-block-phone,
      .cv-block-address,
      .cv-block-email,
      .cv-block-linkedin,
      .cv-block-github {
        font-weight: $light;
        font-size: 1.7rem;
        margin-top:0;
        margin-bottom:0;
      }
    }

    &-section__personal-detail{
      text-align: right;
      .cv-block__wrapper{
        font-family: $raleway;
        color: $greylight-2;
      }
      .cv-block-placedatebirth, 
      .cv-block-gender, 
      .cv-block-language, 
      .cv-block-religion{
        font-weight: $light;
        line-height: .8;
        .value{
          font-weight: $bold;
          color: $black;
        }
      }
    }
  }
</style>