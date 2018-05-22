<template>
  <div class="cv-section__block-inner">
    <div class="" v-if="mainLoaded==false">
      <loading></loading>
    </div>
    <div class="cv-decorator__font-fam">
      <transition-group name="list" tag="div">
        <div v-for="(m, index) in main" v-bind:key="`m-${index}`" class="list-item">
          <p class="cv-section__name-profile ">{{m.nameProfile}}</p>
          <p class="cv-section__job-title ">{{m.jobTitle}}</p>
          <p class="cv-section__phone ">
            Phone: {{m.phone}}
          </p>
          <p class="cv-section__address">
            Address: {{m.address}}
          </p>
          <p class="cv-section__linkedin">
            <a :href="m.linkedin" target="_blank">{{m.linkedin}}</a>
          </p>
          <p class="cv-section__github">
            <a :href="m.github" target="_blank">{{m.github}}</a>
          </p>
          <p class="cv-section__blog">
            <a :href="m.blog" target="_blank">{{m.blog}}</a>
          </p>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'main-profile',
  props: ['main', 'mainLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/variables.scss';

  .cv-section{
    &__name-profile{
      font-size: 2.4rem;
      letter-spacing: 1px;
    }

    &__job-title{
      font-size: 2rem;
      letter-spacing: 1px;
    }

    &__phone{

    }

    &__address{

    }

    &__linkedin{

    }

    &__github{

    }

    &__blog{

    }
  }
</style>