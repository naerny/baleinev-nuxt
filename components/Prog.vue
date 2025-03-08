<script setup>
import { ref } from 'vue';
import { scenes as initialScenes } from '../assets/artists.js';

const scenes = ref(initialScenes);
const activeScene = ref(scenes.value[0]);
const activeArtist = ref(null);

const selectScene = (scene) => {
    activeScene.value = scene;
    activeArtist.value = null; // Reset active artist when switching scenes
};

const toggleLineup = (scene) => {
    scene.showLineup = !scene.showLineup;
};

const showArtistDescription = (artist) => {
    activeArtist.value = artist;
};
</script>

<template>
    <section class="section-prog section-margin" id="prog">
        <div class="container">
            <div class="row">
                <div class="col-12 col-lg-8 offset-lg-2">
                    <h2>Programmation</h2>                    
                </div>
            </div>
            <div class="row tabs">
                <div class="col-12 col-lg-8 offset-lg-2">                  
                    <button v-for="scene in scenes" :key="scene.name" @click="selectScene(scene)"
                        :class="{ active: scene === activeScene }" class="h4">
                        {{ scene.name }}
                    </button>
                   
                </div>
            </div>
            <div class="row">
                <div v-if="!activeScene.showLineup" class="col-12 col-lg-8 offset-lg-2">                    
                    <div v-if="activeScene.name === 'Grande scène'">
                        <p class="h3">Le line up {{ activeScene.name }} arrive Bientôt!</p>
                        <p>Stay tuned!</p>
                    </div>
                    <button v-else class="btn btn__primary h4" @click="toggleLineup(activeScene)">Découvrir le line up {{ activeScene.name }}</button>
                </div>
                <div v-else class="row">                   
                    <a href="#return" v-if="!activeArtist" class="col-12 col-md-6 col-lg-4 artist__container" v-for="artist in activeScene.artists" :key="artist.name" @click="showArtistDescription(artist)">                        
                        <div class="artist__card">
                            <img :src="artist.img" alt="{{ artist.name }}">
                        <div class="artist__cardText">
                            <h3>{{ artist.name }}</h3>
                        <p>{{ artist.style
                            }} - {{ artist.country }}</p>
                        </div>
                        </div>
                    </a>   
                    <div v-else class="row">            
                    <div  class="col-12 col-lg-8 offset-lg-2">
                        <button class="btn btn__lineup" id="return" @click="activeArtist = null">Retourner au lineup</button>
                        <div class="artist__header">
                            <img :src="activeArtist.img" alt="{{ activeArtist.name }}">
                            <div class="artist__headerCopy">
                                <h3 class="h2">{{ activeArtist.name }}</h3>
                            <p class="h3">{{ activeArtist.style
                            }} - {{ activeArtist.country }}</p>
                            </div>
                        </div>
                       
                        <p class="artist__description">{{ activeArtist.description }}</p>
                    </div>
                </div>  
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
@use '../assets/css/main.scss' as *;

.tabs div {
    display: flex;
    // gap: 1rem;
    margin-bottom: 1rem;
}

.tabs button {
    padding: 1rem 2rem;
    cursor: pointer;
    background-color: #f0f0f0;
    border: none;
    color: $color-black;
    margin-bottom: 0;

   @media(max-width: 768px) {
        font-size: 1rem;
    }

    &:hover {
        background: $color-yellow;
    }

    @media(min-width: 768px) {
        padding: 2rem 3rem;
    }
}

.tabs button.active {
    background: $color-yellow;

}

.row {
    margin-bottom: 0;
}

.btn__lineup {
    margin-bottom: $space-md;
    margin-top: $space-sm;
}

button {
    // padding: 0.5rem 1rem;
    // cursor: pointer;
    // background-color: #007bff;
    // color: white;
    // border: none;
    // border-radius: 4px;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    // margin: 0.5rem 0;
    // cursor: pointer;
}

img {
    width: 100%;
    height: auto;
}

.artist {
    &__container {
        text-decoration: none;        
    }
    &__card {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        border-radius: 1rem;
        overflow: auto;
        margin: 0 $space-sm $space-sm;              
        &:hover {
           cursor: pointer;
           transform: scale(1.05) rotate(1deg);
        }

        * {
            color: $color-black !important;               
        }    
        
        @media(min-width: 768px) {
            margin: 0 0 $space-md;
        }
    }

    &__cardText {
        padding: $space-sm;
        background: $color-salmon-light
    }

    &__header {
        display: flex;
        flex-direction: column;
        gap: $space-sm;
        margin-bottom: $space-md;

        @media(min-width: 768px) {
            flex-direction: row;
            gap: $space-md;
        }

        img {
            max-width: 800px;
            border-radius: 2rem;

            @media(min-width: 768px) {
                max-width: 400px;
            }
        }
    }

    &__headerCopy {
        display: flex;
        flex-direction: column;
        justify-content: center;        
    }
}
</style>