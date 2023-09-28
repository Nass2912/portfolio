<template>
    <main>
        <div class="content">
            HEY, I'M ANAS,BUT YOU CAN CALL ME NASS 😉
        </div>
        <div class="sub-content">
            A Full Stack Software Engineer always on the lookout for opportunities <br> to explore and <del>break</del> build new stuff 🛠️
        </div>
        <div class="btn">
            <v-btn variant="outlined" @click="$parent.$emit('test')">
                Projects
            </v-btn>
        </div>
    </main>
</template>

<style lang="scss" scoped>
  @import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,800;1,600&display=swap');
  main {
    scroll-margin-top: 250px;
    height: 92vh;
    @media only screen and (min-width: 600px) {
        height: 76vh;
    }
  }
.content {
    width:82%;
    text-align: center;
    letter-spacing: 3px;
    color: #000;
    font-family: 'Source Sans 3', sans-serif;
    padding: 3rem 0 2rem 0;
    margin: auto;
    font-size: 35px;
    font-weight: 800;
    @media only screen and (min-width: 600px) {
        margin-top: 15vh;
        font-size: 3.5rem;
        width: 60%;
    }
}
.sub-content {
    font-size: 18px;
    padding: 0 1rem;
    margin: auto;
    color: #333;
    text-align: center;
    width: 100%;
    line-height: 2rem;
}

div.btn{
    margin-top: 3rem;
    text-align: center;
    button {
        width: 58%;
        font-family: 'Source Sans 3', sans-serif;
        height: 3.3rem !important;
        background-color: #C70039;
        color: #fff;
        font-size: 16px;
        @media only screen and (min-width: 600px) {
            width: 18%;
        }
    }
}
    
</style>