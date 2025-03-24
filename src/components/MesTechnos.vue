<script setup>
</script>

<template>
    <div id="skills">
    <h2 class="text-highlight-1 section-title">Mes technos</h2>
    <div id="icons-list">
        <div class="techno-container"> <i class="techno-icon devicon-html5-plain"></i> <br> <span>HTML</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-css3-plain"></i> <br> <span>CSS</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-javascript-plain"></i> <br> <span>JS</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-amazonwebservices-plain-wordmark"></i> <br> <span>AWS</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-php-plain"></i> <br> <span>PHP</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-git-plain"></i> <br> <span>GIT</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-vuejs-plain"></i> <br> <span>VueJS</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-vuetify-line"></i> <br> <span>Vuetify</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-bootstrap-plain"></i> <br> <span>Bootstrap</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-symfony-original"></i> <br> <span>Symphony</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-react-original"></i> <br> <span>React</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-angular-plain"></i> <br> <span>Angular</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-mysql-original"></i> <br> <span>MySql</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-postgresql-plain"></i> <br> <span>PostgrSql</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-nuxtjs-plain"></i> <br> <span>NuxtJs</span></div>
        <div class="techno-container"> <i class="techno-icon devicon-nestjs-original"></i> <br> <span>NesJs</span></div>
    </div>
    </div>

</template>

<style scoped>
    #skills {
        margin-top: 60px;
    }
    #icons-list {
        display: grid;
        grid-template-columns: repeat(8, 1fr);
        grid-template-rows: repeat(2, 1fr);
        grid-column-gap: 5px;
        grid-row-gap: 50px;
        margin-top: 35px;
    }
    .techno-container {
        text-align: center;
        color: var(--vt-v-custom-text-1);
        transition: 0.5ms;
    }

    .techno-container span{
        font-weight: bold;
    }

    .techno-container:hover {
        transform: rotate(15deg);
        color: var(--vt-v-custom-text-2) ;
    }
    .techno-icon {
        font-size: 80px;
    }

@media screen and (max-width: 905px){
    #icons-list {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: repeat(4, 1fr);
        grid-column-gap: 5px;
        grid-row-gap: 40px;
    }
}
@media screen and (max-width: 450px){
    #icons-list {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(8, 1fr);
        grid-column-gap: 5px;
        grid-row-gap: 20px;
    }    
}    
</style>
