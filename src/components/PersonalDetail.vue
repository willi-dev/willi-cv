<template>
  <div class="">
    <title-section title="Personal Detail"></title-section>
    <div class="cv-container__loader" v-if="personalLoaded==false">
      <loading></loading>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(person, index) in personal" v-bind:key="`person-${index}`" class="list-item">
        Place, Date of Birth <span class="value">{{person.placeBirth}}, {{person.dateOfBirth}}</span>
        Gender <span class="value">{{person.gender}}</span>
        Language <span class="value">{{person.language}}</span>
        Religion <span class="value">{{person.religion}}</span>
      </div>
    </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'personal-detail',
  props: ['personal', 'personalLoaded'],
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