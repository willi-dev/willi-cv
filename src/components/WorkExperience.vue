<template>
  <div class="">
    <title-section title="Work Experience"></title-section>
    <div class="cv-container__loader" v-if="workLoaded==false" >
			<loading></loading>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(exp, index) in work.slice().reverse()" :key="`exp-${index}`" class="list-item">
          {{exp.position}} | {{exp.company}} <span class="duration">{{exp.period}}</span> 
      </div>
    </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'work-experience',
  props: ['work', 'workLoaded'],
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