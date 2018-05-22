<template>
  <div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Work Experience"></title-section>
    <div class="cv-container__loader" v-if="workLoaded==false" >
			<loading></loading>
    </div>
    <div class="cv-decorator__font-fam cv-container__list">
      <transition-group name="list" tag="ol">
        <li v-for="(exp, index) in work.slice().reverse()" :key="`exp-${index}`" class="list-item">
          <p class="cv-section__work-position ">{{exp.position}} | {{exp.period}}</p> 
          <p class="cv-section__work-company ">{{exp.company}}</p> 
          <p class="cv-section__work-desc ">{{exp.description}}</p>
        </li>
      </transition-group>
    </div>
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
  @import '../assets/scss/variables.scss';
</style>