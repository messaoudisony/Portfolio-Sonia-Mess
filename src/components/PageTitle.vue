<script setup>
import SocialIcon from './SocialIcon.vue'
</script>

<template>

    <div id="top-line">
        <img id="profile-img"  src ="../assets/me.png" alt="me" width="300px" height="280px">
        <div id="line">
            <p> Je suis <span class="text-highlight-1 ">Sonia MESSAOUDI</span>, <br>
            Concepteur developpeur d'application</p>
            <div id="social">
                <SocialIcon img="linkedin" alt="linkedin" link ="https://www.linkedin.com/in/sonia-messaoudi-60a19776/"/>
                <SocialIcon img="github" alt="linkedin" link ="https://github.com/messaoudisony/Portfolio-Sonia-Mess"/>
                <SocialIcon img="gitlab" alt="linkedin" link ="https://gitlab.com//"/>
                
            </div>
        </div>
    </div>
    
</template>

<style scoped>

    #top-line{
        margin-top: 50px;
        width: 100%;
        height: 300px;
    }
    #top-line #profile-img{
        float: left;
        margin-right: 50px;
    }

    #top-line #line{
        float: left;
        transform: translateY(40%);
        text-align: center;
    }

    #top-line p {
        font-size: 37px;
        line-height: 60px;
        overflow-wrap: break-word;
    }

    #top-line p span {
        font-weight: bold;
    }

    #social{
        margin-top: 15px;
    }

@media screen and (max-width: 805px) {
    #profile-img {
        display: none !important;
    }
    #top-line #line {
        float: none !important;
        transform: translateY(0%) !important;
    }
    #top-line p {
        font-size: 32px !important;
    }
}

</style>