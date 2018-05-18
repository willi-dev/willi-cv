<template>
  <div class="">
    Project
    <div class="cv-container__loader" v-if="projectLoaded==false" >
      <beat-loader></beat-loader>
    </div>
    <transition-group name="list" tag="div">
      <div v-for="(prj, index) in project.slice().reverse()" :key="`prj-${index}`" class="list-item">
        {{prj.name}} | {{prj.company}} <span class="duration">{{prj.period}}</span>
          <p>{{prj.description}}</p>
      </div>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'project',
  props: ['project', 'projectLoaded'],
};
</script>

<style lang="scss">
  
</style>