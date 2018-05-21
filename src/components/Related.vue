<template>
  <div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Related Development Tools"></title-section>
    <div class="cv-container__loader" v-if="relatedLoaded==false">
      <loading></loading>
    </div>
    <transition-group name="list" tag="span">
      <span v-for="(rel, index) in related.slice().reverse()" v-bind:key="`rel-${index}`" class="cv-item v-item__tools cv-decorator__font-fam">
        {{rel.relatedtools}}
      </span>
    </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'related',
  props: ['related', 'relatedLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  @import '../assets/scss/variables.scss';
</style>