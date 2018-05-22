<template>
  <p class="cv-section__title cv-decorator__font-title">{{title}}</p>
</template>

<script>
export default {
  name: 'title-section',
  props: ['title'],
};
</script>

<style lang="scss">
@import '../../assets/scss/variables.scss';

.cv{
  &-section__title{
    font-size: 2.4rem;
    letter-spacing: 1px;
  }
}

</style>