<template>
  <div class="cv-section__block-inner cv-section__personal-detail">
    <title-section title="Main Profile"></title-section>
    <div class="" v-if="mainLoaded==false">
      <loading></loading>
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
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'main-profile',
  props: ['main', 'mainLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/cv-variables.scss';
</style>