<script setup>
import { ref } from 'vue'

let activeBloc = ref(0);
let experiences = ref([
    {
        title: "Technicienne FTTH",
        date: "2018- 2023",
        line1: "Installation et maintenance de réseaux de fibre optique",
        line2: "Résolution de problèmes techniques et service client",
        line3: "Coordination avec les équipes techniques et les clients pour assurer une prestation de qualité."
    },
    {
        title: "Chargée d'Appel d'Offres",
        date: "2014 - 2015",
        line1: "Gestion des appels d'offres et des propositions commerciales",
        line2: "Analyse des besoins clients et élaboration des réponses adaptées",
        line3: "Coordination avec les équipes internes pour la préparation des offres"
    }
]);

    const showXp = (id) => {
        activeBloc.value = id
    };


</script>

<template>
    <div id="xp">
        <h2 class="text-highlight-1 section-title">Experiences</h2>
        <div id="left">
            <p :class="activeBloc === 0 ? 'active' : ''" class="company fw600" @click="showXp(0)">FREE</p>
            <p :class="activeBloc === 1 ? 'active' : ''" class="company fw600" @click="showXp(1)">IVAL IVECO</p>
        </div>

        <div id="right">
            <template v-for="(job, index) in experiences">
                <div class="job-details" :class="index === activeBloc ? '' : 'hide'" :id="'bloc_'+index"> 
                    <h3 class="fw600 " > {{  job.title }}</h3>
                    <span id="date"> {{ job.date }}</span>
                    <br>
                    <p class="fw600 mtb8" style="margin-top: 10px;"><span class="text-highlight-2">✓</span> {{ job.line1 }}</p>
                    <p class="fw600 mtb8" > <span class="text-highlight-2">✓</span> {{ job.line2 }}</p>
                    <p class="fw600 mtb8" > <span class="text-highlight-2">✓</span> {{ job.line3 }}</p>
                </div>
            </template>
        </div>
    </div>
</template>

<style scoped>
    #xp { 
        margin-top: 60px;
    }

    #xp #left {
        float: left;
        width: 25%;
    }

    #xp #right{
        float: left;
        width: 75%;
    }

    #xp #right #h3 {
        font-size: 20px;
    }

    .mtb8 {
        margin: 8px 0px;
    }

    #date {
        font-style: italic;
        font-size: 14px;
    }
    .company {
        border-left: 4px solid var(--vt-v-custom-text-1);
        line-height: 30px;
        padding-left: 10px;
    }

    .active {
        border-left: 4px solid var(--vt-v-custom-text-2);
        color: var(--vt-v-custom-text-2);
    }

    .company:hover {
        cursor: pointer;
        color: var(--vt-v-custom-text-1);
    }

    .hide {
        display: none;
    }

    @media screen and (max-width: 600px) {
        #xp #right {
            width: 100%;
            margin-top: 20px;
        }
        #xp #left {
            width: 100%;
        }

        .company {
            border: none;
            padding-left: 0px;
            float: left;
            margin-right: 10px;
        }
    }    
</style>
