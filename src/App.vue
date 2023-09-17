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
  <chatBtn/>
</template>

<script>
import navbar from './components/navbar.vue'
import Home from './components/Home.vue'
import chatBtn from './components/chatBtn.vue'
import aboutMe from './components/aboutMe.vue'
import projectPage from './components/projectPage.vue'
import contactMe from './components/contactMe.vue'
import footerVue from './components/footerVue.vue'

export default {
  name: 'App',

  components: {
    navbar,
    Home,
    chatBtn,
    aboutMe,
    projectPage,
    contactMe,
    footerVue
  },
  methods: {
    logger(){
      this.$refs.ProjectRef.$el.scrollIntoView({behavior: "smooth"});
    },
    aboutlogger(){
      this.$refs.ContactRef.$el.scrollIntoView({behavior: "smooth"});
    },
    redirectNav(params){
      console.log(params)
      const constructedRef = `${params}Ref`
      this.$refs[constructedRef].$el.scrollIntoView({behavior: "smooth"});
    }
  }
}
</script>
