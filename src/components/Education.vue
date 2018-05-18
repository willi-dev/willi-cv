<template>
	<div class="">
    Education
    <div class="cv-container__loader" v-if="eduLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="edu in education.slice().reverse()" v-bind:key="edu.school" class="list-item">
            {{edu.school}}
            {{edu.period}}
            {{edu.description}}
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