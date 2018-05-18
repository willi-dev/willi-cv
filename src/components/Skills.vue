<template>
	<div class="">
    <title-section title="Skill"></title-section>
    <div class="cv-container__loader" v-if="skillLoaded==false">
      <loading></loading>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(sk, index) in skills.slice().reverse()" v-bind:key="`sk-${index}`" class="list-item">
        {{sk.skill}}
      </div>
    </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'skills',
  props: ['skills', 'skillLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
	@import '../assets/scss/cv-variables.scss';
  
</style>