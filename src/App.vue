<template>
  <v-app>
    <v-main @main="logger" @aboutFn="aboutlogger" @navBarText="redirectNav">
      <navbar>
        <Home ref="HomeRef"/>
        <aboutMe ref="AboutRef"/>
        <projectPage ref="ProjectRef"/>
        <contactMe ref="ContactRef"/>
        <footerVue/>
      </navbar>
    </v-main>
  </v-app>
  <chatBtn @mainer="tester"/>
  <formModal v-if="modalShow" @closed="modalShow = false" @notify="notifier = true" />
  <v-alert closable text="Download Succesful" variant="outlined" v-if="notifier"></v-alert>
</template>

<script>
import navbar from './components/navbar.vue'
import Home from './components/Home.vue'
import chatBtn from './components/chatBtn.vue'
import aboutMe from './components/aboutMe.vue'
import projectPage from './components/projectPage.vue'
import contactMe from './components/contactMe.vue'
import footerVue from './components/footerVue.vue'
import formModal from './components/formModal.vue'

export default {
  name: 'App',

  data(){
    return {
      modalShow: false,
      notifier: false
    }
  },

  components: {
    navbar,
    Home,
    chatBtn,
    aboutMe,
    projectPage,
    contactMe,
    footerVue,
    formModal
  },
  methods: {
    tester(){
      this.modalShow = true
    },
    logger(){
      this.$refs.ProjectRef.$el.scrollIntoView({behavior: "smooth",});
    },
    aboutlogger(){
      this.$refs.ContactRef.$el.scrollIntoView({behavior: "smooth"});
    },
    redirectNav(params){
      const constructedRef = `${params}Ref`
      this.$refs[constructedRef].$el.scrollIntoView({behavior: "smooth"});
    }
  }
}
</script>

<style scoped >
  .v-alert {
    position: fixed;
    bottom: 2rem;
    left: 1rem;
    background: #C70039;
    color: #fff;
  }
</style>
