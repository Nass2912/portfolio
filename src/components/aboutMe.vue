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
    </main>
</template>

<style scoped>
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