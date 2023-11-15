<template>
  <v-app>
    <v-main @main="logger" @aboutFn="aboutlogger" @navBarText="redirectNav">
      <navbar>
        <Home
          ref="HomeRef"
          v-motion
          :initial="{
            x: -100,
            opacity: 0,
          }"
          :enter="{
            x: 0,
            opacity: 1,
            transition: {
              type: 'spring',
              stiffness: 100,
              damping: 50,
              mass: 0.5,
            },
          }"
        />
        <aboutMe 
          ref="AboutRef"
          v-motion
          :delay="200"
          :initial="{
            opacity: 0,
            x: -100,
          }"
          :visible="{
            opacity: 1,
            x: 0,
            transition: {
              type: 'spring',
              stiffness: 100,
              damping: 50,
              mass: 0.5,
            },
          }"
        />
        <projectPage 
          ref="ProjectRef"
          v-motion
          :delay="200"
          :initial="{
            opacity: 0,
            x: -100,
          }"
          :visible="{
            opacity: 1,
            x: 0,
            transition: {
              type: 'spring',
              stiffness: 100,
              damping: 50,
              mass: 0.5,
            },
          }"
        />
        <contactMe 
          ref="ContactRef"
          v-motion
          :delay="200"
          :initial="{
            opacity: 0,
            x: -100,
          }"
          :visible="{
            opacity: 1,
            x: 0,
            transition: {
              type: 'spring',
              stiffness: 100,
              damping: 50,
              mass: 0.5,
            },
          }"
        />
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
