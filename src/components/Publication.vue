<template>
	<div class="">
    Publication Research
    <div class="cv-container__loader" v-if="publicationLoaded==false">
      <beat-loader></beat-loader>  
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(p, index) in publication.slice().reverse()" v-bind:key="`p-${index}`" class="list-item">
        {{p.publication}}
        {{p.description}}
        {{p.link}}
      </div>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'publication',
  props: ['publication', 'publicationLoaded'],
};
</script>

<style lang="scss">
  @import '../assets/scss/cv-variables.scss';
  
</style>