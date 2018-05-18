<template>
  <div class="cv-section__block-inner cv-section__personal-detail">
    
    <div class="cv-container__loader" v-if="mainLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(m, index) in main" v-bind:key="`m-${index}`" class="list-item">
        {{m.nameProfile}}
        {{m.jobTitle}}
        {{m.phone}}
        {{m.address}}
        {{m.linkedin}}
        {{m.github}}
        {{m.blog}}
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'main-profile',
  props: ['main', 'mainLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/cv-variables.scss';
</style>