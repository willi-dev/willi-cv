<template>
	<div class="cv-section__block-inner cv-section__publication-research">
    <h3 class="cv-section__block-title">Publication Research</h3>
    <div class="cv-container__loader" v-if="publicationLoaded==false">
      <beat-loader></beat-loader>  
    </div>
    <transition-group name="list" tag="div">
      <div v-for="p in publication.slice().reverse()" v-bind:key="p.publication" class="list-item">
        <div class="cv-block__wrapper cv-block__wrapper-publication-type">
          <h4 class="cv-block-publication-type cv-block-text">
            {{p.publication}}
          </h4>
        </div>
        <div class="cv-block__wrapper cv-block__wrapper-publication-description">
          <h4 class="cv-block-publication-description cv-block-text">
            {{p.description}}
          </h4>
        </div>
        <div class="cv-block__wrapper cv-block__wrapper-publication-url">
          <h4 class="cv-block-publication-url cv-block-text">
            {{p.link}}
          </h4>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'publication',
  props: ['publication', 'publicationLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  @import '../assets/scss/cv-variables.scss';
  .cv{
    &-section__publication-research{
      text-align: left;
      font-family: $raleway;
      .cv-block__wrapper{
        font-family: $raleway;
        color: $greydark;
      }
      .cv-block-text{
        font-weight: $light;
        // line-height: .8;
      }
      .cv-block-publication-type{
        color: $greydark;
        font-weight: $normal;
      }
      .cv-block-publication-url{
        color: $greydark;
        font-weight: $normal;
      }
      .cv-block-publication-type,
      .cv-block-publication-title,
      .cv-block-publication-description{
        margin-bottom: 0;
      }
      .cv-block-publication-title,
      .cv-block-publication-description,
      .cv-block-publication-url{
        margin-top: 0;
      }
      .cv-block-publication-title,
      .cv-block-publication-url{
        margin-top: .2rem;
      }
    }
  }
</style>