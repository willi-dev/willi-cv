<template>
	<div class="cv-section__block-inner cv-section__skills">
    <h3 class="cv-section__block-title">Skills</h3>
    <div class="cv-container__loader" v-if="skillLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="skill in skills" v-bind:key="skill" class="list-item">
        <div class="cv-block__wrapper cv-block__wrapper-skills-main">
          <h4 class="cv-block-skills-main cv-block-text">
            {{skill.main_skills}}
          </h4>
        </div>
        <div class="cv-block__wrapper cv-block__wrapper-skills-related">
          <h3 class="cv-block-skills-related-title cv-block-text">Related Development Tools</h3>
          <h4 class="cv-block-skills-related cv-block-text">
            {{skill.related_tools}}
          </h4>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'skills',
  props: ['skills', 'skillLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
	@import '../assets/scss/cv-variables.scss';
  .cv{
    &-section__skills{
      text-align: right;
      font-family: $raleway;
      .cv-block__wrapper{
        font-family: $raleway;
        color: $black;
      }
      .cv-block-text{
        font-weight: $light;
        line-height: 1;
      }
      .cv-block-skills-main{
        margin-bottom: 0;
      }
      .cv-block-skills-related-title{
        color: $greylight-2;
        font-size: 2.1rem;
        margin-top: 0;
        margin-bottom: 0;
      }
      .cv-block-skills-related{
        margin-top: 0;
      }
    }
  }
</style>