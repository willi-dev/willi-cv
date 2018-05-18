<template>
  <div class="">
    <title-section title="Project"></title-section>
    <div class="cv-container__loader" v-if="projectLoaded==false" >
      <loading></loading>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(prj, index) in project.slice().reverse()" :key="`prj-${index}`" class="list-item">
        {{prj.name}} | {{prj.company}} <span class="duration">{{prj.period}}</span>
          <p>{{prj.description}}</p>
      </div>
    </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'project',
  props: ['project', 'projectLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  
</style>