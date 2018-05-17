<template>
  <div class="cv-section__block-inner cv-section__skills">
    <h3 class="cv-section__block-title">Related</h3>
    <div class="cv-container__loader" v-if="relatedLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="rel in related" v-bind:key="rel.relatedtools" class="list-item">
        <div class="cv-block__wrapper cv-block__wrapper-skills-main">
          <h4 class="cv-block-skills-main cv-block-text">
            {{rel.relatedtools}}
          </h4>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'related',
  props: ['related', 'relatedLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
  
</style>