<template>
  <div class="cv-section__block-inner cv-section__work-experience">
    <h3 class="cv-section__block-title">Project</h3>
    <div class="cv-container__loader" v-if="projectLoaded==false" >
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="prj in project.slice().reverse()" :key="prj.name" class="list-item">
        <div class="cv-block__wrapper cv-block__wrapper-company">
          <h4 class="cv-block-company cv-block-text">{{prj.name}} | {{prj.company}} <span class="duration">{{prj.period}}</span></h4>  
          <p>{{prj.description}}</p>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'project',
  props: ['project', 'projectLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  
</style>