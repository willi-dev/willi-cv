<template>
	<div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Publication Research"></title-section>
    <div class="cv-container__loader" v-if="publicationLoaded==false">
      <loading></loading>
    </div>
    <div class="cv-decorator__font-fam cv-container__list">
      <transition-group name="list" tag="ol">
        <li v-for="(p, index) in publication.slice().reverse()" v-bind:key="`p-${index}`" class="list-item">
          <p class="cv-section__publication-name">{{p.publication}}</p>
          <p class="cv-section__publication-desc">{{p.description}}</p>
          <p class="cv-section__publication-link">
            <a :href="p.link" target="_blank">{{p.link}}</a>
          </p>
        </li>
      </transition-group>
    </div>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'publication',
  props: ['publication', 'publicationLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  @import '../assets/scss/variables.scss';
  
</style>