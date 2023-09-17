<template>
  <v-app>
    <v-main @main="logger" @aboutFn="aboutlogger">
      <navbar>
        <Home/>
        <aboutMe/>
        <projectPage ref="mainRef"/>
        <contactMe ref="contactRef"/>
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
      this.$refs.mainRef.$el.scrollIntoView({behavior: "smooth"});
    },
    aboutlogger(){
      this.$refs.contactRef.$el.scrollIntoView({behavior: "smooth"});
    }
  }
}
</script>
