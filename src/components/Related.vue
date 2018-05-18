<template>
  <div class="">
    <title-section title="Related"></title-section>
    <div class="cv-container__loader" v-if="relatedLoaded==false">
      <loading></loading>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(rel, index) in related.slice().reverse()" v-bind:key="`rel-${index}`" class="list-item">
        {{rel.relatedtools}}
      </div>
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
  
</style>