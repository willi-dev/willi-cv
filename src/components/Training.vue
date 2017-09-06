<template>
	<div class="cv-section__block-inner cv-section__training">
    <h3 class="cv-section__block-title">Training</h3>
    <div class="cv-container__loader" v-if="trainingLoaded==false">
	    <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
	    <div v-for="train in training" v-bind:key="train.name" class="list-item">
	    	<div class="cv-block__wrapper cv-block__wrapper-training-name">
	    		<h4 class="cv-block-training-name cv-block-text">{{train.name}}</h4>
	    	</div>
	    	<div class="cv-block__wrapper cv-block__wrapper-training-year">
	    		<h4 class="cv-block-training-year cv-block-text">{{train.place_year}}</h4>
	    	</div>
	    </div>
	  </transition-group>
  </div>
</template>

<script>
import BeatLoader from '../../node_modules/vue-spinner/src/BeatLoader';

export default {
  name: 'training',
  props: ['training', 'trainingLoaded'],
  components: {
    BeatLoader,
  },
};
</script>

<style lang="scss">
	@import '../assets/scss/cv-variables.scss';
	.cv{
		&-section__training{
			text-align: right;
			font-family: $raleway;
			@media screen and (max-width: 767px){
        text-align: left;
      }
			.cv-block__wrapper{
				font-family: $raleway;
				color: $greylight-3;
			}
			.cv-block-text{
				font-weight: $light;
				line-height: .8;
			}
			.cv-block-training-name{
				color: $black;
				font-weight: $bold;
			}
		}
	}
</style>