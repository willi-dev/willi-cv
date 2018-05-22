<template>
	<div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Training"></title-section>
    <div class="cv-container__loader" v-if="trainingLoaded==false">
	    <loading></loading>
    </div>
    <div class="cv-decorator__font-fam cv-container__list">
      <transition-group name="list" tag="ol">
  	    <li v-for="(train, index) in training.slice().reverse()" v-bind:key="`train-${index}`" class="list-item">
          <p class="cv-section__training-name">
            {{train.name}} ( {{train.year}} )
          </p>
          <p class="cv-section__training-place">{{train.place}}</p>
  	    </li>
  	  </transition-group>
    </div>
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
	@import '../assets/scss/variables.scss';
	
</style>