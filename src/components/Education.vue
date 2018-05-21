<template>
	<div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Education"></title-section>
    <div class="cv-container__loader" v-if="eduLoaded==false">
      <loading></loading>
    </div>
    <div class="cv-decorator__font-fam cv-container__list">
    <transition-group name="list" tag="ol">
      <li v-for="edu in education.slice().reverse()" v-bind:key="edu.school" class="cv-list__item">
        <p class="cv-section__school">
          {{edu.school}}  
          <span class="cv-section__period">({{edu.period}})</span>
        </p>
        <p class="cv-section__description">
          {{edu.description}}
        </p>
      </li>
    </transition-group>
    </div>
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
  @import '../assets/scss/variables.scss';
  
</style>