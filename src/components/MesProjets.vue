<script setup>
import { ref } from 'vue';
import ProjectSingle from '@/components/ProjectSingle.vue'

let projects = ref([
    {
        name: "Escape-game",
        image: "web.jpg",
        tags: "HTML; CSS; JavaScript",
        description: "un jeu web inspiré de l'univers  de Harry Potter et de Rick et Morty, où les utilisateurs doivent résoudre des puzzles.",
        task: "Développement de l'interface utilisateur en utilisant React,; création de composants réutilisables,; Implémentation de la logique du jeu."
    },
    {
        name: "React-calendar-style",
        image: "web.jpg",
        tags: "React; CSS",
        description: "La librairie de composants Calendrier est une collection de composants pré-construits et réutilisables conçue pour simplifier l'intégration de calendriers dans les applications React.",
        task: "Creer des composants modulaires tels que Day, Week, Month.; faciliter la construction de calendriers flexibles.; Utiliser Story Book pour la documentation"
    },
    {
        name: "Wild-chat",
        image: "web.jpg",
        tags: "HTML; CSS; JavaScript",
        description: "Développement d'un jeu web inspiré de l'univers magique de Harry Potter et de l'humour décalé de Rick et Morty, où les utilisateurs doivent résoudre des puzzles pour avancer.",
        task: "Développement de l'interface utilisateur en utilisant React,; création de composants réutilisables,; utilisation de CSS et animations."
    },
    {
        name: "Orbit-Partners",
        image: "web.jpg",
        tags: "HTML; CSS; JavaScript",
        description: "Développement d'un jeu web inspiré de l'univers magique de Harry Potter et de l'humour décalé de Rick et Morty, où les utilisateurs doivent résoudre des puzzles pour avancer.",
        task: "Développement de l'interface utilisateur en utilisant React,; création de composants réutilisables,; utilisation de CSS et animations."
    }
]);

</script>

<template>
    <div id="projets">
        <h2 class="text-highlight-1 section-title">Quelques projets</h2>
        <ProjectSingle v-for="(project, index) in projects" :key="projects.name" :project="project" :reverse="index % 2 === 0 ? false : true " />
    </div>
</template>

<style scoped>
#projets {
    display: inline-block;
    margin-top: 60px;
}
</style>
