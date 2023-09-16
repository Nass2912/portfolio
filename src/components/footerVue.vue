<template>
    <div class="main">
        <div class="title bolder">
            SOCIAL
        </div>
        <div class="icons">
          <a href="https://github.com/Nass2912" target="_blank"><i class="fa-brands fa-github"></i></a>
          <a href="https://linkedin.com/in/soobrattyanas" target="_blank"><i class="fa-brands fa-linkedin"></i></a>
        </div>
        <div class="note bolder">
            NASS
            <div class="subnote">
                A Software Engineer looking for the one app that is going to make a difference
            </div>
        </div>
        <div class="thank">
            © Copyright {{ year }} Made with ♡ by Nass
        </div>
    </div>
</template>

<script>
  export default {
    data: () => ({
      year: new Date().getFullYear(),
    }),
  }
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,400;1,600&display=swap');
  .main {
    .bolder {
      font-weight: 800;
    }
    .icons {
      i {
        color: #fff;
        margin-top: 1.5rem;
        margin-bottom: 2rem;
        margin-right: 1rem;
      }
    }
    background-color: #000;
    color: #fff;
    padding: 2rem 1rem;
    font-family: 'Source Sans 3', sans-serif;
    font-size: 18px;
    .subnote {
      margin-top: 1rem;
      font-size: 14px;
      font-weight: 400;
    }
    .thank {
      text-align: center;
      margin: 3rem 0;
      margin-bottom: 0;
      position: relative;
      font-size: 11px;
      &::after{
        content: "";
        position: absolute;
        bottom: 2rem;
        margin-left: auto;
        margin-right: auto;
        left: 0;
        right: 0;
        text-align: center;
        border-radius: 10%;
        border-top: 1px solid #fff;
      }
    }
  }
</style>