<template>
  <v-app>
    <v-main>
      <navbar>
        <Home/>
        <aboutMe/>
        <projectPage/>
        <contactMe/>
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
}
</script>
