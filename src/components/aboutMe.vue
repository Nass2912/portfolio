<template>
    <main>
        <div class="content">
        ABOUT ME
        </div>
        <div class="sub-content">
            
          Here you will find more information about me, what I do, and my
          current skills mostly in terms of programming and technology
        
        </div>
        <div class="body-content">
            <h1 class="title">Get to know me!</h1>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Fuga facere ipsum nam incidunt laborum omnis sed sequi odio voluptatibus? Amet earum, necessitatibus quam vel, quas hic modi nihil quia, suscipit quasi in et impedit facere dicta doloremque voluptates rem architecto! Praesentium id, eveniet quae excepturi voluptas rerum voluptate vel tempora!</p>
        </div>
        <div class="btn">
            <v-btn variant="outlined" @click="$parent.$emit('about')">
                Contact
            </v-btn>
        </div>
        <div class="body-content">
            <h1 class="title">My Stack</h1>
            <div class="flex-container">
                <div class="flex-item">Vue</div>
                <div class="flex-item">APIs</div>
                <div class="flex-item">React</div>
                <div class="flex-item">Javascript</div>
                <div class="flex-item">AWS</div>
                <div class="flex-item">Ruby on Rails</div>
                <div class="flex-item">Github Actions</div>
                <div class="flex-item">PostgreSQL</div>
                <div class="flex-item">NodeJs</div>
                <div class="flex-item">HTML</div>
                <div class="flex-item">SCSS</div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,500;1,600&display=swap');
    main {
        padding-bottom: 2rem;
    }
    .flex-container {
        display: flex;
        flex-wrap: wrap;
        .flex-item {
            font-family: 'Source Sans 3', sans-serif;
            font-size: 14px;
            margin: 10px;
            margin-left: 0;
            padding: 10px;
            border-radius: 10%;
            background-color: #EFEFEF;
        }
    }

    .body-content {
        margin: 3rem 1rem;
        padding: 0 1rem;
        .title {
            margin-bottom: 2rem;
            text-align: left;
            font-size: 18px;
        }
    }
    .sub-content {
        margin:1rem 2rem;
        line-height: 1.5rem;
        text-align: center;
    }
    main {
        background-color: #fff;
        .btn{
        margin-left: 1rem;
        margin-top: 3rem;
        text-align: left;
        button {
            width: 50%;
            font-family: 'Source Sans 3', sans-serif;
            height: 3rem !important;
            background-color: #C70039;
            color: #fff;
            font-size: 16px;
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
</style>