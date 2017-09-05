<template>
  <div class="cv-section__block-inner cv-section__work-experience">
    <h3 class="cv-section__block-title">Work Experience</h3>
    <div class="cv-container__loader" v-if="workLoaded==false" >
			<beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="exp in work" :key="exp" class="list-item">
        <div class="cv-block__wrapper cv-block__wrapper-company">
          <h4 class="cv-block-company cv-block-text">{{exp.position}} | {{exp.company}} <span class="duration">{{exp.duration}}</span></h4>  
        </div>
        <!-- {{ exp.projects }} -->
        <div v-for="(proj, index) in exp.projects" class="cv-block__wrapper cv-block__wrapper-projects">
          <div v-for="(projitem, key) in proj">
            <div v-if="key=='title'" class="cv-block__wrapper cv-block__wrapper-project-title">
              <h4 class="cv-block-project-title cv-block-text">Project: {{projitem}}</h4>
            </div> 
            <div v-if="key=='desc'" class="cv-block__wrapper cv-block__wrapper-project-desc">
              <h4 class="cv-block-project-desc cv-block-text">{{projitem}}</h4>
            </div>
            <div v-if="key=='url'" v-show="projitem!='-'" class="cv-block__wrapper cv-block__wrapper-project-url">
              <h4 class="cv-block-project-url cv-block-text">{{projitem}}</h4>
            </div>
          </div>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'work-experience',
  props: ['work', 'workLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/cv-variables.scss';
  .cv{
    &-section__work-experience{
      text-align: left;
      .cv-block__wrapper{
        font-family: $raleway;
        color: $greydark;
      }
      .cv-block__wrapper-projects{
        padding-left: .5rem;
        font-size: 1.3rem;
      }
      .cv-block-company{
        font-weight: $bold;
        .duration{
          font-weight: $normal;
          color: $greylight-2;
        }
      }
      .cv-block-project-title,
      .cv-block-project-desc,
      .cv-block-project-url{
        font-size: 1.5rem;
        color: $greylight-1;
        font-weight: $light;
      }
      // .cv-block-project-title{
      //   font-weight: $normal;
      // }
      .cv-block-project-title,
      .cv-block-project-desc{
        margin-top: 0;
        margin-bottom: 0;
      }
      .cv-block-project-url{
        margin-top: 0;
      }
    }
  }
</style>