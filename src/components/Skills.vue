<template>
	<div class="">
    Skills
    <div class="cv-container__loader" v-if="skillLoaded==false">
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(sk, index) in skills.slice().reverse()" v-bind:key="`sk-${index}`" class="list-item">
        {{sk.skill}}
      </div>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'skills',
  props: ['skills', 'skillLoaded'],
};
</script>

<style lang="scss">
	@import '../assets/scss/cv-variables.scss';
  
</style>