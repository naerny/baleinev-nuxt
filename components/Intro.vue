<script setup>
import { onMounted } from 'vue'
import BlvLogo from '../assets/svg/blv-logo-full.svg'
import SpaceShip from '../assets/svg/spaceship-date.svg'
import Planet1 from '../assets/svg/planet1.svg'
import planet2 from '../assets/svg/planet2.svg'
import Planet3 from '../assets/svg/planet3.svg'

const daysBefore = (date) => {
    const now = new Date();
    const eventDate = new Date(date);
    const diffTime = eventDate - now;
    const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
    return diffDays;
}

onMounted(() => {
    const headerHeight = document.querySelector('header').offsetHeight;
    console.log("headerHeight", headerHeight);

    const intro = document.querySelector('.intro');
    // intro.style.height = `calc(100vh - ${headerHeight}px - 2rem)`;
    // intro.style.maxHeight = `calc(100vh - ${headerHeight}px - 2rem)`;
});
</script>

<template>
    <section class="section-intro">
        <div class="container">
            <div class="intro">
                <div class="intro__left">
                    <SpaceShip class="spaceship" />
                </div>
                <div class="intro__right">
                    <BlvLogo class="logo" />
                    <h2 class="text-shadow">31<sup>ème</sup> édition</h2>
                </div>
                <div class="intro__btns">
                    <div class="btn__copy">
                        <h3>Baleinev 2025, c'est dans <span class="text-shadow">{{ daysBefore('2025-05-02') }} jours!</span></h3>
                        <!-- <p class="h4 text-shadow">La billeterie est ouverte!</p> -->
                        <p class="h5 text-shadow">Découvre le line up!</p>
                    </div>
                    <div class="btn__ticket">
                        <a class="btn btn__primary btn__big" href="#prog">Découvrir la prog</a>
                    </div>
                    <!-- <a class="btn btn__secondary btn__big" href="#volunteers">Devenir bénévole</a> -->
                    <a class="btn btn__secondary btn__big" href="#ticketing">Billetterie</a>
                </div>
            </div>
        </div>
        <div class="planet__container container">
            <Planet1 class="planet planet1" />
            <planet2 class="planet planet2" />
            <Planet3 class="planet planet3" />
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "./assets/css/main.scss" as *;

@keyframes moveRandomly {
    0% {
        transform: translate(0, 15px);
    }

    20% {
        transform: translate(5px, -15px);
    }

    40% {
        transform: translate(5px, 15px);
    }

    60% {
        transform: translate(-2px, -15px);
    }

    80% {
        transform: translate(15px, 15px);
    }

    100% {
        transform: translate(5, -10);
    }
}

.intro {
    display: flex;
    flex-wrap: wrap;
    min-height: calc(100vh - 80px); 
    padding: $space-sm 0;

    @media (min-width: 768px) {
        // flex-direction: row;
        // justify-content: flex-start;
        // min-height: 80vh;
    }

    @media(min-width: 1200px) {
        padding: $space-lg 0;
    }

    &__left {
        padding: 0 $space-sm;
        width: 50%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        height: auto;

        @media (max-width: 991px) {
            width: 100%;
        }

        @media (min-width: 1200px) {
            transform: translateX(-10%);
        }
    }

    &__right {
        padding: 0 $space-sm;
        width: 50%;

        @media (max-width: 991px) {
            order: -1;
            width: 100%;
        }
    }

    &__btns {
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin-top: auto;

        gap: $space-sm;

        @media(min-width: 768px) {
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: center;
            align-items: end;
        }
    }
}

.btn__primary {
    position: relative;
}

.btn__ticket {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;

    p {
        font-weight: 700;
    }
}

.btn__copy {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.logo {
    width: 100%;
    max-width: 100%;
    height: auto;
}

.spaceship {
    width: 100%;
    max-width: 100%;
    height: auto;
    animation: moveRandomly 15s infinite alternate;

    @media (min-width: 768px) {
        width: 50%;
    }

    @media (min-width: 992px) {
        width: 100%;
    }


}

.planet {
    position: absolute;
    min-width: 200px;
    height: auto;
    z-index: -1;
}

.planet1 {
    top: 10%;
    left: 10%;

    @media (min-width: 1200px) {
        left: 20%;
    }

    @media (min-width: 2200px) {
        left: 40%;
    }
}

.planet2 {
    bottom: 10%;
    right: 10%;
    min-width: 275px;

    @media (min-width: 1200px) {
        right: 20%;
    }

    @media (min-width: 2200px) {
        right: 30%;
    }
}

.planet3 {
    top: 60%;
    left: 5%;
    min-width: 150px;

    @media (min-width: 1200px) {
        left: 20%;
    }

    @media (min-width: 2200px) {
        left: 30%;
    }
}

h2 {
    color: $color-yellow !important;
    font-size: 2.5rem !important;
    margin-top: .5em !important;

    @media(min-width: 768px) {
        font-size: 3rem !important;
    }
}

h3 {
    justify-content: center;
    text-align: center;

    span {
        color: $color-yellow !important;
    }
}
.h4 {
    color: $color-yellow !important;
}
</style>