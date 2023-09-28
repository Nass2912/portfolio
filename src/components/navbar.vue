<template>
    <v-card >
      <v-layout>
        <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->
  
        <v-app-bar
          color="primary"
          prominent
        >
        <img class="mx-2" src="../assets/pfpic.png"/>
        <v-toolbar-title>NASS</v-toolbar-title>
        <div class="container" @click.stop="myFunction" v-if="isMobile">
          <div class="bar1"></div>
          <div class="bar2"></div>
          <div class="bar3"></div>
        </div>
        <v-app-bar-nav-icon v-if="isMobile" variant="text"></v-app-bar-nav-icon>
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
    isMobile: false,
    crossMobile: '',
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
    drawer() {
      if(!this.drawer){
        this.crossMobile.classList.remove("change");
      }
    }
  },
  mounted(){
    this.isMobile = window.innerWidth < 600
    window.addEventListener('resize', () => {
      this.isMobile = window.innerWidth < 600
    })
  },
  methods: {
    myFunction(event){
      this.drawer = !this.drawer
      this.crossMobile = event.currentTarget
      this.crossMobile.classList.add("change");
    },
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
      this.crossMobile.classList.add("change");
      this.$parent.$emit('navBarText',$event.target.innerText)
    }
  }
}
</script>

<style lang="scss">
div.container {
  position: absolute;
  right: 1rem;
  background: #fff;
  z-index: 123;
}
.bar1, .bar2, .bar3 {
  width: 35px;
  height: 3px;
  background-color: #000;
  margin: 6px 0;
  transition: 0.4s;
}

.change .bar1 {
  transform: translate(0, 6px) rotate(-45deg);
}

.change .bar2 {opacity: 0;}

.change .bar3 {
  transform: translate(0, -11px) rotate(45deg);
}
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
      .v-btn {
        visibility: hidden;
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