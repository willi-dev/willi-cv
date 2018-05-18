<template>
	<div class="">
    <title-section title="Education"></title-section>
    <div class="cv-container__loader" v-if="eduLoaded==false">
      <loading></loading>
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
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'education',
  props: ['education', 'eduLoaded'],
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