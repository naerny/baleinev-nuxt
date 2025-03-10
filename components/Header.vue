<script setup>
import { ref, onMounted } from 'vue';
import BlvIcon from '../assets/svg/blv-icon.svg';

const isMenuOpen = ref(false);
// const body = ref(null);

// onMounted(() => {
//    body = document.querySelector('body');
// });

const toggleMenu = () => {
   isMenuOpen.value = !isMenuOpen.value;
   document.body.classList.toggle('no-scroll');
};
</script>

<template>
   <header>
      <div class="container">
         <div class="row">
            <nav>
               <BlvIcon class="icon" />
               <button class="burger" @click="toggleMenu">
                  <span class="burger__line"></span>
                  <span class="burger__line"></span>
                  <span class="burger__line"></span>
               </button>
               <div :class="{ 'menu': true, 'menu--open': isMenuOpen }">
                  <a href="#ticketing" class="link btn">Billeterie</a>
                  <a href="#prog" class="link">Programme</a>
                  <a href="#volunteers" class="link">Devenir bénévole</a>
               </div>
            </nav>
         </div>
      </div>
   </header>
</template>

<style scoped lang="scss">
@use "./assets/css/main.scss" as *;

nav {
   display: flex;
   align-items: center;
   gap: $space-sm;
   width: 100%;
   padding: $space-sm 0;
   margin: 0 $space-sm;
   border-bottom: 1px solid $color-white;

   .link {
      font-weight: 700;
   }

   .icon {
      width: 48px;
      height: 48px;
      margin-right: auto;
   }

   .burger {
      display: none;
      flex-direction: column;
      justify-content: space-around;
      width: 24px;
      height: 24px;
      background: none;
      border: none;
      cursor: pointer;
      padding: 0;

      &__line {
         width: 100%;
         height: 2px;
         background-color: $color-white;
      }
   }

   .menu {
      display: flex;
      align-items: center;
      gap: $space-sm;


      &--open {
         right: 0;
         transition: all 0.3s ease-out;

      }
   }

   @media (max-width: 600px) {
      .burger {
         display: flex;
         z-index: 30;
         right: -100%;
         transition: all 0.3s ease-out;
      }

      .menu {
         z-index: 20;
         // display: none;
         align-items: center;
         flex-direction: column;
         gap: $space-sm;
         position: absolute;
         top: 0;
         right: 0;
         width: 100%;
         height: 100%;
         opacity: 0;
         background-color: $color-lila;
         padding: $space-lg $space-sm;
         transition: all 0.3s ease-out;

         &--open {
            display: flex;
            right: 0;
            opacity: 1;
         }
      }
   }
}
</style>