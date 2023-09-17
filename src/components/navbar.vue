<template>
    <v-card >
      <v-layout>
        <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->
  
        <v-app-bar
          color="primary"
          prominent
        >
        <v-img
            class="mx-2"
            src="src/assets/pfpic.png"
            max-height="40"
            max-width="40"
            cover
        ></v-img>
        <v-toolbar-title>NASS</v-toolbar-title>
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        </v-app-bar>
  
        <v-navigation-drawer
          v-model="drawer"
          location="right"
          temporary
        >
          <v-list
            :items="items"
          ></v-list>
        </v-navigation-drawer>
  
        <v-main @test="clickfn" @about="aboutClick">
            <slot></slot>
        </v-main>
      </v-layout>
    </v-card>
  </template>

<script scoped>
export default {
  data: () => ({
    drawer: false,
    group: null,
    items: [
      {
        title: 'Home',
        value: 'Home',
      },
      {
        title: 'About',
        value: 'About',
      },
      {
        title: 'Project',
        value: 'Project',
      },
      {
        title: 'Contact',
        value: 'Contact',
      },
    ],
  }),

  watch: {
    group () {
      this.drawer = false
    },
  },
  methods: {
    clickfn(){
      this.$parent.$emit('main')
    },
    aboutClick(){
      this.$parent.$emit('aboutFn')
    }
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@1,700&display=swap');
    .v-layout {
      background-color: #EFEFEF;
        .v-toolbar__content {
            background-color: #fff;
            .v-toolbar-title__placeholder {
                font-family: 'Source Sans 3', sans-serif;
                color: #000;
                font-size: 16px;
            }
            .v-btn__content {
                color: #000;
            }
            .v-responsive {
                margin-right: 0 !important;
            }
        }
        .v-img__img {
            border-radius: 50%;
            border: 1px solid #000;
        }
    }
</style>