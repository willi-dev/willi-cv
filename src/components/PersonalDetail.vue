<template>
  <div class="cv-decorator__border-bottom cv-decorator__padding-y">
    <title-section title="Personal Detail"></title-section>
    <div class="cv-container__loader" v-if="personalLoaded==false">
      <loading></loading>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(person, index) in personal" v-bind:key="`person-${index}`" class="list-item">
        <p class="cv-section__placedob cv-decorator__font-fam">
          Place, Date of Birth: <span class="value">{{person.placeBirth}}, {{person.dateOfBirth}}</span>
        </p>
        <p class="cv-section__gender cv-decorator__font-fam">
          Gender: <span class="value">{{person.gender}}</span>
        </p>
        <p class="cv-section__language cv-decorator__font-fam">
          Language: <span class="value">{{person.language}}</span>
        </p>
        <p class="cv-section__religion cv-decorator__font-fam">
          Religion: <span class="value">{{person.religion}}</span>
        </p>
      </div>
    </transition-group>
  </div>
</template>

<script>
import Loading from './general/Loading';
import TitleSection from './general/TitleSection';

export default {
  name: 'personal-detail',
  props: ['personal', 'personalLoaded'],
  components: {
    Loading,
    TitleSection,
  },
};
</script>

<style lang="scss">
  // always load in every component for read variables
  @import '../assets/scss/variables.scss';
</style>