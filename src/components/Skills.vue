<template>
	<div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Skill"></title-section>
    <div class="cv-container__loader" v-if="skillLoaded==false">
      <loading></loading>
    </div>
    <transition-group name="list" tag="span">
      <span v-for="(sk, index) in skills.slice().reverse()" v-bind:key="`sk-${index}`" class="cv-item cv-item__skill cv-decorator__font-fam">
        {{sk.skill}}
      </span>
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
	@import '../assets/scss/variables.scss';
  

</style>