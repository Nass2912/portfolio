<template>
    <main>
        <div class="test">
            <div class="content">
            ABOUT ME
            </div>
            <div class="sub-content">
                
              Here you will find more information about me, what I do, and my
              current skills mostly in terms of programming and technology
            
            </div>
            <div class="body-content">
                <h1 class="title">Get to know me!</h1>
                <p>I worked many jobs since my teenage years, be it delivery helper, website moderator, interior design and what not. Being a very curious person by nature and having that urge to always know how things work, I was presented with a great opportunity at Le Wagon to do a coding bootcamp. For me that rang a bell, "hey we'll finally know how the web works!".<br><br> Since end of 2021,when I finished my bootcamp till now, I have been fascinated by the sofware engineering world and I have been able to contribute to some awesome projects and to also give back to the community through teaching at Le Wagon.<br><br> My hobbies are varied but it always ends up falling into a sports category of some kind or something related to mechanics (bike and cars, recently planes!). I also love to explore the world and I'm probably never going to say no to a hike or a trek to a waterfall ! 😉</p>
            </div>
            <div class="btn">
                <v-btn variant="outlined" @click="$parent.$emit('about')">
                    Let's talk!
                </v-btn>
            </div>
        </div>
        <div class="body-content">
            <h1 class="title">My Stack</h1>
            <div class="flex-container">
                <div class="flex-item">VueJs</div>
                <div class="flex-item">React</div>
                <div class="flex-item">Javascript</div>
                <div class="flex-item">AWS</div>
                <div class="flex-item">Ruby on Rails</div>
                <div class="flex-item">Github Actions</div>
                <div class="flex-item">PostgreSQL</div>
                <div class="flex-item">NodeJs</div>
                <div class="flex-item">APIs </div>
                <div class="flex-item">HTML</div>
                <div class="flex-item">SCSS</div>
            </div>
        </div>
        <BadgeEmbed/>
    </main>
</template>

<script>
import BadgeEmbed from './badgeEmbed.vue';

export default {
  components: {
    BadgeEmbed,
  },
};
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,500;1,600&display=swap');
    main {
        padding-bottom: 2rem;
        scroll-margin-top: 10px;
    }
    .flex-container {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        @media only screen and (min-width: 600px) {
            width: 80vw;
            margin: 0 auto;
        }

        .flex-item {
            font-family: 'Source Sans 3', sans-serif;
            font-size: 14px;
            margin: 10px;
            margin-left: 0;
            padding: 10px;
            border-radius: 10%;
            letter-spacing: 2px;
            background-color: #EFEFEF;
            @media only screen and (min-width: 600px) {
                padding: 10px 55px;
                border-radius: 2%;
                letter-spacing: 4px;
            }

        }
    }

    .body-content {
        margin: 3rem 1rem;
        padding: 0 1rem;
        margin: 1rem auto;
        width: 90vw;
        @media only screen and (min-width: 600px) {
            width: 60vw;
            text-align: center;
        }
        .title {
            margin-bottom: 2rem;
            text-align: left;
            font-size: 18px;
            @media only screen and (min-width: 600px) {
                text-align: center;
            }

        }
        p {
            @media only screen and (min-width: 600px) {
                width: 60vw;
                margin: 0 auto;
            }
        }
    }
    .test {
        .body-content {
            // width:
        }
    }
    .sub-content {
        line-height: 1.5rem;
        text-align: center;
        width: 60vw;
        margin: 1rem auto;
        @media(max-width:600px){
        width: unset;
        margin: unset;
        margin: 1rem 2rem
        }
    }
    main {
        background-color: #fff;
        .btn{
        margin-left: 1rem;
        margin-top: 3rem;
        text-align: left;
        @media only screen and (min-width: 600px) {
            text-align: center;
        }
        button {
            width: 50%;
            font-family: 'Source Sans 3', sans-serif;
            height: 3rem !important;
            background-color: #C70039;
            color: #fff;
            font-size: 16px;
            @media only screen and (min-width: 600px) {
                width: 18%;
            }
        }
    }
    }
    .content {
        position: relative;
        width: 82%;
        text-align: center;
        letter-spacing: 3px;
        color: #000;
        font-family: "Source Sans 3", sans-serif;
        padding: 3rem 0 2rem 0;
        margin: auto;
        font-size: 35px;
        font-weight: 800;
        &::after{
            content: "";
            position: absolute;
            bottom: 0;
            margin-left: auto;
            margin-right: auto;
            left: 0;
            right: 0;
            text-align: center;
            height: 0.7em;
            width: 7vw;
            border-radius: 10%;
            border-top: 5px solid #C70039;
        }
    }
    main .body-content {
        width: 100%
    }
</style>