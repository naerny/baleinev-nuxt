<script setup>
import BlvIcon from '../assets/svg/blv-icon.svg'
</script>

<template>
   <header>
      <div class="container">
         <div class="row">
            <nav>
               <BlvIcon class="icon" />
               <!-- <a href="#ticketing" class="link">Billeterie</a> -->
                <a href="#prog" class="link">Programme</a>
               <a href="#volunteers" class="link">Devenir bénévole</a>
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
      // font-family: 'Bebas Bold'
      font-weight: 700;
   }
}

.icon {
   width: 48px;
   height: 48px;
   margin-right: auto;
}
</style>