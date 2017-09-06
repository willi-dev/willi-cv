<template>
	<div class="cv-section__block-inner cv-section__education">
    <h3 class="cv-section__block-title">Education</h3>
      <div class="cv-container__loader" v-if="eduLoaded==false">
        <beat-loader></beat-loader>
      </div>
      <transition-group name="list" tag="div">
        <div v-for="edu in education" v-bind:key="edu" class="list-item">
          <div class="cv-block__wrapper cv-block__wrapper-school">
            <h4 class="cv-block-school cv-block-text">
              {{edu.school}}
            </h4>
          </div>
          <div class="cv-block__wrapper cv-block__wrapper-eduyear">
            <h4 class="cv-block-edu-year cv-block-text">
              {{edu.year}}    
            </h4>
          </div>
          <div v-if=" edu.department!='-' "class="cv-block__wrapper cv-block__wrapper-department">
            <h4 class="cv-block-departement cv-block-text">
              {{edu.department}}
            </h4>
          </div>
        </div>
      </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'education',
  props: ['education', 'eduLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/cv-variables.scss';
  .cv{
    &-section__education{
      text-align: right;
      @media screen and (max-width: 767px){
        text-align: left;
      }
      .cv-block__wrapper{
        font-family: $raleway;
        color: $black;
      }
      .cv-block-school{
        font-weight: $bold;

      }
      .cv-block-edu-year,
      .cv-block-departement{
        font-weight: $light;
        line-height: .8;
      }
      .cv-block-edu-year{
        color: $greylight-2;
      }
      .cv-block-departement{
        color: $black;
      }
    }
  }
</style>