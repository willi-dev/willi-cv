<template>
  <div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Project"></title-section>
    <div class="cv-container__loader" v-if="projectLoaded==false" >
      <loading></loading>
    </div>
    <div class="cv-decorator__font-fam cv-container__list">
      <transition-group name="list" tag="ol">
        <li v-for="(prj, index) in project.slice().reverse()" :key="`prj-${index}`" class="list-item">
          <p class="cv-section__project-name ">{{prj.name}} | {{prj.company}}</p>
          <p class="cv-section__project_period duration">{{prj.period}}</p>
          <p class="cv-section__project-description">{{prj.description}}</p>
        </li>
      </transition-group>
    </div>
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
@import '../assets/scss/variables.scss';

.cv-section{
  &__project-name{
    font-weight: $semi-bold;
    font-size: 1.3rem;
  }
}
</style>