<template>
  <div class="">
    Related
    <div class="cv-container__loader" v-if="relatedLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(rel, index) in related.slice().reverse()" v-bind:key="`rel-${index}`" class="list-item">
        {{rel.relatedtools}}
      </div>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'related',
  props: ['related', 'relatedLoaded'],
};
</script>

<style lang="scss">
  
</style>