<template>
  <v-app>
    <v-main>
      <navbar>
        <Home/>
        <aboutMe/>
        <projectPage/>
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

export default {
  name: 'App',

  components: {
    navbar,
    Home,
    chatBtn,
    aboutMe,
    projectPage
  },
}
</script>
