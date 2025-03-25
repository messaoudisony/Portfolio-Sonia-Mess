<script setup>
    import { ref, onMounted, onUnmounted } from 'vue';

    const props = defineProps({
        project: {
            type: Object,
            required: true
        },
        reverse: {
            type: Boolean,
            required: false
        }
    });

    let fadeInElements = ref();

    // Ajouter l'écouteur d'événement pour le scroll
    onMounted(() => {
        fadeInElements.value = Array.from(document.getElementsByClassName('fade-in'));
        document.addEventListener('scroll', handleScroll);
    });

    // Enlever l'écouteur d'événements lors du démontage du composant
    onUnmounted(() => {
        document.removeEventListener('scroll', handleScroll);
    });

    // Fonction de gestion du scroll
    const handleScroll = () => {
        for (let i = 0; i < fadeInElements.value.length; i++) {
            const elem = fadeInElements.value[i];
            if (isElemVisible(elem)) {
                elem.style.opacity = '1';
                elem.style.transform = 'scale(1)';
                fadeInElements.value.splice(i, 1);  // Retirer l'élément après l'animation
            }
        }
    };

    // Vérifier si un élément est visible dans le viewport
    const isElemVisible = (el) => {
        const rect = el.getBoundingClientRect();
        const elemTop = rect.top + 200;  // 200px avant le bas de l'élément pour déclencher l'animation
        const elemBottom = rect.bottom;
        return elemTop < window.innerHeight && elemBottom >= 0;
    };

    // Fonction pour récupérer les tags du projet
    const getProjectTags = () => {
        return props.project.tags.split(';');
    };

    // Fonction pour récupérer les tâches du projet
    const getProjectTask = () => {
        return props.project.task.split(';');
    };
</script>

<template>
    <div class="project">
        <div class="left fade-in" :class="reverse ? 'reverse' : ''">
            <h3 class="text-highlight-1">{{ project.name }}</h3>
            <a :href="`src/assets/${project.image}`" target="_blank">
                <img :src="`src/assets/${project.image}`" :alt="project.name">
            </a>
        </div>

        <div class="right fade-in">
            
            <p class="tag" v-for="tag in getProjectTags()" :key="tag">{{ tag }}</p>
            
            <p class="description">
                {{ project.description }}
            </p>
            
            <p class="task">
                <span v-for="task in getProjectTask()" :key="task">
                    <span class="text-highlight-2">✓</span> {{ task }}<br/>
                </span>
            </p>
        </div>
    </div>
</template>

<style scoped>
    .project {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(1, 1fr);
        grid-column-gap: 20px;
        grid-row-gap: 50px;
        margin-top: 35px;
    }

    .project .left h3 {
        font-weight: bold;
        font-size: 20px;
        margin-bottom: 10px;
    }

    .project .left img {
        width: 100%;
    }

    .project .right {
        padding-top: 42px;
    }

    .project .right .tag {
        display: block;
        float: left;
        background-color: #333746;
        padding: 8px 16px;
        margin-right: 12px;
        border-radius: 5px;
        font-weight: bold;
    }

    .project .right .description {
        clear: both;
        margin-top: 50px;
        font-size: 17px;
    }

    .project .right .task {
        margin-top: 20px;
        font-size: 17px;
    }

    .reverse {
        order: 1;
    }
    
    .fade-in {
        opacity: 0;
        transition: 0.3s all ease-out;
        transform: scale(0.8);  
        display: inline-block;
    }

    .fade-in.visible {
        opacity: 1;
        transform: scale(1); 
    }

    @media screen and (max-width: 905px) {
        .project {
            grid-template-columns: repeat(1, 1fr);
            grid-template-rows: repeat(1, 1fr);
            grid-column-gap: 0px;
            grid-row-gap: 20px;
        }

        .project .right {
            padding-top: 0px;
        }

        .reverse {
            order: 0;
        }
    }

    @media screen and (max-width: 450px) {
        .project .right .tag {
            margin-bottom: 10px;
        }
    }
</style>
