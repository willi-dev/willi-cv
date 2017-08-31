<template>
	<div class="cv-section__block-inner cv-section__education">
    <h3 class="cv-section__block-title">Education</h3>
    <div v-for="edu in education">
    	{{edu.department}}
    	{{edu.year}}
    	{{edu.school}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'education',
  props: ['education'],
};
</script>

<style lang="scss"></style>