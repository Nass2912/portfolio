<template>
    <div>   
      <div class="custom-model-main" :class="{'model-open': isOpen}">
          <div class="custom-model-inner">        
          <div class="close-btn" @click="closeElement">×</div>
              <div class="custom-model-wrap">
                  <div class="pop-up-content-wrap">
                    <p>
                        Confirm Résume Download ? 
                    </p>
                    <v-btn @click="downloader">
                        Confirm
                    </v-btn>
                  </div>
              </div>  
          </div>  
          <div class="bg-overlay" @click="closeElement"></div>
      </div> 
    </div>
  </template>
  
  <script>
  export default {
    data(){
      return {
        isOpen: true,
        downloadSuccess: false
      }
    },
    methods:{
      elementOpen() {
        this.isOpen = true;
      },
      closeElement() {
        this.$emit("closed")
        this.isOpen = false;
      },
      downloader(event){
        event.preventDefault()
        
        this.downloadFile("https://drive.usercontent.google.com/u/0/uc?id=1ZN-4yLXqXb_Web_LtDXJAL6I90Q1LTyW&export=download")
        setTimeout(() => {
            this.$emit("closed", true)
        }, 200);
      },
      downloadFile(filePath){
        const link=document.createElement('a');
        link.href = filePath;
        link.download = filePath.substr(filePath.lastIndexOf('/') + 1);
        link.click();
      }
    }
  }
  </script>
  
  <style scoped>
  .pop-up-content-wrap {
    .v-btn {
        margin-top: 1rem;
        background-color: #C70039;
        color: #fff;
    }
  }
  .custom-model-main {
    text-align: center;
    overflow: hidden;
    position: fixed;
    top: 40%;
    right: 0;
    left: 0; /* z-index: 1050; */
    -webkit-overflow-scrolling: touch;
    outline: 0;
    opacity: 0;
    -webkit-transition: opacity 0.15s linear, z-index 0.15;
    -o-transition: opacity 0.15s linear, z-index 0.15;
    transition: opacity 0.15s linear, z-index 0.15;
    z-index: -1;
    overflow-x: hidden;
    overflow-y: auto;
  }
  
  .model-open {
    z-index: 99999;
    opacity: 1;
    overflow: hidden;
  }
  .custom-model-inner {
    -webkit-transform: translate(0, -25%);
    -ms-transform: translate(0, -25%);
    transform: translate(0, -25%);
    -webkit-transition: -webkit-transform 0.3s ease-out;
    -o-transition: -o-transform 0.3s ease-out;
    transition: -webkit-transform 0.3s ease-out;
    -o-transition: transform 0.3s ease-out;
    transition: transform 0.3s ease-out;
    transition: transform 0.3s ease-out, -webkit-transform 0.3s ease-out;
    display: inline-block;
    vertical-align: middle;
    width: 600px;
    margin: 30px auto;
    max-width: 97%;
  }
  .custom-model-wrap {
    display: block;
    width: 100%;
    position: relative;
    background-color: #fff;
    border: 1px solid #999;
    border: 1px solid rgba(0, 0, 0, 0.2);
    border-radius: 6px;
    -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
    box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
    background-clip: padding-box;
    outline: 0;
    text-align: left;
    padding: 20px;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    max-height: calc(100vh - 70px);
      overflow-y: auto;
  }
  .model-open .custom-model-inner {
    -webkit-transform: translate(0, 0);
    -ms-transform: translate(0, 0);
    transform: translate(0, 0);
    position: relative;
    z-index: 999;
  }
  .model-open .bg-overlay {
    background: rgba(0, 0, 0, 0.6);
    z-index: 99;
  }
  .bg-overlay {
    background: rgba(0, 0, 0, 0);
    height: 100vh;
    width: 100%;
    position: fixed;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: 0;
    -webkit-transition: background 0.15s linear;
    -o-transition: background 0.15s linear;
    transition: background 0.15s linear;
  }
  .close-btn {
    position: absolute;
    right: 7px;
    top: 0;
    cursor: pointer;
    z-index: 99;
    font-size: 30px;
    color: #C70039;
  }
  
  @media screen and (min-width:800px){
      .custom-model-main:before {
        content: "";
        display: inline-block;
        height: auto;
        vertical-align: middle;
        margin-right: -0px;
        height: 100%;
      }
  }
  @media screen and (max-width:799px){
    .custom-model-inner{margin-top: 45px;}
  }
  
  p{
    font-size: 15px;
    padding: 0 3px;
  }
  
  </style>