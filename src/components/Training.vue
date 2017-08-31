<template>
	<div class="cv-section__block-inner cv-section__training">
    <h3 class="cv-section__block-title">Training</h3>
    <div v-for="train in training">
    	{{train.name}}
    	{{train.place_year}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'training',
  props: ['training'],
};
</script>

<style lang="scss"></style>