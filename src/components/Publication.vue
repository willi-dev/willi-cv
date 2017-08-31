<template>
	<div class="cv-section__block-inner cv-section__publication-research">
    <h3 class="cv-section__block-title">Publication Research</h3>
    <div v-for="p in publication">
    	{{p.type}}
    	{{p.title}}
    	{{p.description}}
    	{{p.url}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'publication',
  props: ['publication'],
};
</script>

<style lang="scss"></style>