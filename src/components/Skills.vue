<template>
	<div class="cv-section__block-inner cv-section__skills">
    <h3 class="cv-section__block-title">Skills</h3>
    <div v-for="skill in skills">
    	{{skill.main_skills}}
    	{{skill.related_tools}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'skills',
  props: ['skills'],
};
</script>

<style lang="scss">
	
</style>