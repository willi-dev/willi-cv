<template>
  <div id="app">
    <div class="container cv-container__app">
      <div class="row">
        <div class="col-xs-12 col-md-6 col-md-offset-3">
          <div class="cv-section__block--left cv-section__block">
            <main-profile :main="main" :mainLoaded="mainLoaded"></main-profile>
            <personal-detail :personal="personal" :personalLoaded="personalLoaded"></personal-detail>
            <education :education="education" :eduLoaded="eduLoaded"></education>
            <skills :skills="skills" :skillLoaded="skillLoaded"></skills>
            <related :related="related" :relatedLoaded="relatedLoaded"></related>
            <training :training="training" :trainingLoaded="trainingLoaded"></training>
            <workExperience :work="work" :workLoaded="workLoaded"></workExperience>
            <project :project="project" :projectLoaded="projectLoaded"></project>
            <publication :publication="publication" :publicationLoaded="publicationLoaded"></publication>
          </div>  
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
import Firebase from '../node_modules/firebase';
import MainProfile from './components/MainProfile';
import PersonalDetail from './components/PersonalDetail';
import Education from './components/Education';
import Skills from './components/Skills';
import Related from './components/Related';
import Training from './components/Training';
import WorkExperience from './components/WorkExperience';
import Project from './components/Project';
import Publication from './components/Publication';
import VueSticky from '../node_modules/vue-sticky';
import config from './services/firebase';

const app = Firebase.initializeApp(config);
const db = app.database();
const dataMainProfile = db.ref('mainprofile');
const dataPersonalDetail = db.ref('personaldetail');
const dataEducation = db.ref('education');
const dataSkills = db.ref('skill');
const dataRelated = db.ref('related');
const dataTraining = db.ref('training');
const dataWork = db.ref('work');
const dataProject = db.ref('project');
const dataPublication = db.ref('publication');

export default {
  name: 'app',
  components: {
    mainProfile: MainProfile,
    personalDetail: PersonalDetail,
    education: Education,
    skills: Skills,
    related: Related,
    training: Training,
    workExperience: WorkExperience,
    project: Project,
    publication: Publication,
  },
  firebase: {
    main: {
      source: dataMainProfile,
      readyCallback: function mainReady() {
        this.mainLoaded = true;
      },
    },
    personal: {
      source: dataPersonalDetail,
      readyCallback: function personalReady() {
        this.personalLoaded = true;
      },
    },
    education: {
      source: dataEducation,
      readyCallback: function educationReady() {
        this.eduLoaded = true;
      },
    },
    skills: {
      source: dataSkills,
      readyCallback: function skillsReady() {
        this.skillLoaded = true;
      },
    },
    related: {
      source: dataRelated,
      readyCallback: function relatedReady() {
        this.relatedLoaded = true;
      },
    },
    training: {
      source: dataTraining,
      readyCallback: function trainingReady() {
        this.trainingLoaded = true;
      },
    },
    work: {
      source: dataWork,
      readyCallback: function workReady() {
        this.workLoaded = true;
      },
    },
    project: {
      source: dataProject,
      readyCallback: function projectReady() {
        this.projectLoaded = true;
      },
    },
    publication: {
      source: dataPublication,
      readyCallback: function publicationReady() {
        this.publicationLoaded = true;
      },
    },
  },
  data() {
    return {
      mainLoaded: false,
      personalLoaded: false,
      eduLoaded: false,
      skillLoaded: false,
      relatedLoaded: false,
      trainingLoaded: false,
      workLoaded: false,
      projectLoaded: false,
      publicationLoaded: false,
      stickyConfig: {
        zIndex: 100,
        stickyTop: 20,
      },
    };
  },
  directives: {
    sticky: VueSticky,
  },
};
</script>

<style lang="scss">
  // always load
  @import './assets/scss/typography.scss';
  // always load in every component for read variables
  @import './assets/scss/variables.scss';
  
  p, ol, ul{
    margin: 0;
  }

  .cv-container{
    &__app{
      padding-top: 20px;
      padding-bottom: 20px;
    }

    &__list{
      ol{
        padding-left: 2rem;
      }

    }
  }

  .cv-decorator{

    &__font-title{
      font-family: $lato;

    }
    &__font-fam{
      font-family: $tienne;
      font-size: 1.2rem;
      // color: $greylight-1;
    }

    &__padding-y{
      padding: 1rem 0;
    }
    &__padding-top{
      padding-top: 1rem;
    }
    &__padding-bottom{
      padding-bottom: 1rem;
    }

    
    &__border-bottom{
      border-bottom: 1px dashed $greylight-3;
    }
  }
  


  .cv-item{
    margin: 0 4px;
    text-decoration: underline;
  }

</style>