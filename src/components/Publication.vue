<template>
	<div class="">
    <title-section title="Publication Research"></title-section>
    <div class="cv-container__loader" v-if="publicationLoaded==false">
      <loading></loading>
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
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'publication',
  props: ['publication', 'publicationLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  @import '../assets/scss/cv-variables.scss';
  
</style>