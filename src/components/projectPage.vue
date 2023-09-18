<template>
    <main>
        <div class="content">
        PROJECTS
        </div>
        <div class="sub-content">
            
          Here you will find some professional project I worked on, personal project and a lot of trial and error!
        
        </div>
        <div class="projects__row-img-cont">
            <img class="try" src="src/assets/angelaw.png">
            <div class="body-content">
                <h1 class="title"><a target="_blank" href="https://www.angelaw.fr/">Angelaw</a></h1>
                <p>Contract management software for startups and SMEs. Tech used was VueJs, AWS and Laravel mainly</p>
            </div>
        </div>
        <div class="projects__row-img-cont">
            <img class="try" src="src/assets/merco.png">
            <div class="body-content">
                <h1 class="title"><a target="_blank" href="https://www.mercedes-benz.co.uk/passengercars/being-an-owner/service-plan.html/">Mercedes UK</a></h1>
                <p>Creating a platform for owners to buy serviceplans according to their car registration numbers. JAM Stack Application with microservice architecture deployed on AWS and VueJs and typescript as Front end, as well as contentul as CMS</p>
            </div>
        </div>
        <div class="projects__row-img-cont">
            <img class="try" src="src/assets/rails_recipe.png">
            <div class="body-content">
                <h1 class="title"><a target="_blank" href="https://github.com/Nass2912/rails_react_recipe">Rails and React</a></h1>
                <p>Messing around with merging the powerful Rails Framework with a front end framework to discover the full capabilites of a neo-web app</p>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,500;1,600&display=swap');
    main {
        scroll-margin-top: 10px;
        background-color: #fff;
        @media only screen and (min-width: 600px) {
            background-color: #fafafa;
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
    .body-content {
        padding: 0 1rem;
        text-align: center;
        h1 {
            margin: 2rem;
            font-size: 16px;
            font-family: "Source Sans 3", sans-serif;
            text-align: center;
            color: #000;
        }
        p {
            font-size: 15px;
        }
    }
    .projects__row-img-cont{
        @media only screen and (min-width: 600px) {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 80%;
            margin: 0 auto;
            background-color: #fafafa;
        }
        .body-content {
            @media only screen and (min-width: 600px) {
                width: 50vw;
            }
        }
        margin-bottom: 2rem;
        background-color: #FAFAFA;
        img {
            overflow: hidden;
            height: auto;
            width: 100vw;
            @media only screen and (min-width: 600px) {
                width: 50vw;
            }
        }
    }

    .sub-content {
        margin:1rem 2rem;
        line-height: 1.5rem;
        text-align: center;
    }
</style>