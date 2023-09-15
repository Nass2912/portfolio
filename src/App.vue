<template>
  <v-app>
    <v-main>
      <navbar>
        <Home/>
        <chatBtn/>
      </navbar>
    </v-main>
  </v-app>
</template>

<script>
import navbar from './components/navbar.vue'
import Home from './components/Home.vue'
import chatBtn from './components/chatBtn.vue'

export default {
  name: 'App',

  components: {
    navbar,
    Home,
    chatBtn
  },
}
</script>
