<template>
	<div class="">
    <title-section title="Training"></title-section>
    <div class="cv-container__loader" v-if="trainingLoaded==false">
	    <loading></loading>
    </div>
    <transition-group name="list" tag="div">
	    <div v-for="(train, index) in training.slice().reverse()" v-bind:key="`train-${index}`" class="list-item">
        {{train.name}},{{train.place}}, ( {{train.year}} )
	    </div>
	  </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'training',
  props: ['training', 'trainingLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
	@import '../assets/scss/cv-variables.scss';
	
</style>