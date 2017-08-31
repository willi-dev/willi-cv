<template>
  <div class="cv-section__block-inner cv-section__work-experience">
    <h3 class="cv-section__block-title">Work Experience</h3>
    <div v-for="experience in work">
      {{experience.company}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'work-experience',
  props: ['work'],
};
</script>

<style lang="scss"></style>