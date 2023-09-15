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
            <img src="https://d33wubrfki0l68.cloudfront.net/19c708670a1f21231c1e2efa6ba38dbf52b15343/3237e/assets/jpeg/dopefolio.jpeg" alt="Software Screenshot" class="projects__row-img" loading="lazy">
            <div class="body-content">
                <h1 class="title"><a target="_blank" href="https://www.angelaw.fr/">Angelaw</a></h1>
                <p>Contract management software for startups and SMEs. Tech used was VueJs, AWS and Laravel mainly</p>
            </div>
        </div>
        <div class="projects__row-img-cont">
            <img class="try" src="src/assets/merco.png">
            <img src="https://d33wubrfki0l68.cloudfront.net/19c708670a1f21231c1e2efa6ba38dbf52b15343/3237e/assets/jpeg/dopefolio.jpeg" alt="Software Screenshot" class="projects__row-img" loading="lazy">
            <div class="body-content">
                <h1 class="title"><a target="_blank" href="https://www.mercedes-benz.co.uk/passengercars/being-an-owner/service-plan.html/">Mercedes UK</a></h1>
                <p>Creating a platform for owners to buy serviceplans according to their car registration numbers. JAM Stack Application with microservice architecture deployed on AWS and VueJs and typescript as Front end, as well as contentul as CMS</p>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,500;1,600&display=swap');
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
        position: relative;
        margin-bottom: 2rem;
        .try {
            object-fit: fill;
            position: absolute;
            right: 37px;
            top: 17px;
            height: 187px;
            width: 301px;
        }
        img {
            overflow: hidden;
            height: auto;
            width: 100vw;
        }
    }

    .sub-content {
        margin:1rem 2rem;
        line-height: 1.5rem;
        text-align: center;
    }
</style>