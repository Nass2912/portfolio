<template>
    <v-card >
      <v-layout>
        <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->
  
        <v-app-bar
          color="primary"
          prominent
        >
        <img
            class="mx-2"
            src="../assets/pfpic.png"
            max-height="40"
            max-width="40"
            cover
        />
        <v-toolbar-title>NASS</v-toolbar-title>
        <v-app-bar-nav-icon v-if="isMobile" variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <div v-if="!isMobile" class="div-to-flex">
          <ul class="unordered"  v-for="item in items" :key="item">
            <li @click="clickerDesktop(item.value)" >{{item.value}}</li>
            
          </ul>
        </div>
      </v-app-bar>
  
        <v-navigation-drawer
          v-model="drawer"
          location="right"
          temporary
        >
          <v-list
            :items="items"
            @click="clicker"
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
    isMobile: false,
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
  mounted(){
    this.isMobile = window.innerWidth < 600
    window.addEventListener('resize', () => {
      this.isMobile = window.innerWidth < 600
    })
  },
  methods: {
    clickfn(){
      this.$parent.$emit('main')
    },
    aboutClick(){
      this.$parent.$emit('aboutFn')
    },
    clickerDesktop(params){
      this.$parent.$emit('navBarText',params)
    },
    clicker($event){
      this.drawer = false
      this.$parent.$emit('navBarText',$event.target.innerText)
    }
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@1,700&display=swap');
    .div-to-flex {
      display: flex;
    }
    .v-toolbar__content{
      & img {
        &.mx-2 {
          cursor: pointer;
          margin-right: 0 !important;
          height: 40px;
          width: 40px;
          border: 1px solid black;
          border-radius: 50%;
          object-fit: cover;
        }
      }
    } 
    .unordered {
      li {
        font-weight: 500;
        color: #000;
        list-style: none;
        margin-right: 2rem;
        transition: 0.3s;
        &:hover{ 
          cursor: pointer;
          color: #C70039;
          opacity: 1;
        }
      }
    }
    .v-layout {
      background-color: #EFEFEF;
      .v-navigation-drawer {
        position: fixed !important;
      }
      .v-toolbar {
        position: fixed !important;
      }
        .v-toolbar__content {
            background-color: #fff;
            .v-toolbar-title__placeholder {
                font-family: 'Source Sans 3', sans-serif;
                color: #000;
                font-size: 16px;
                font-weight: 600;
                &:hover {
                  color: #C70039;
                  cursor: pointer;
                  transition: 0.3s;
                }
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