<script setup>
import sponso01 from '../assets/svg/sponsors/bliblablo.svg'
import sponso02 from '../assets/svg/sponsors/boxer.svg'
import sponso03 from '../assets/svg/sponsors/heig.svg'
import sponso04 from '../assets/svg/sponsors/impactvision.svg'
import sponso05 from '../assets/svg/sponsors/infomaniak.svg'
import sponso06 from '../assets/svg/sponsors/poste.svg'
import sponso07 from '../assets/svg/sponsors/travys.svg'
import sponso08 from '../assets/svg/sponsors/yverdon.svg'
import sponso09 from '../assets/svg/sponsors/elca.svg'
</script>

<template>
   <footer>      
     <div class="container">
      <div class="row">
         <div class="sponsor-container">
         <!-- <sponso01 class="sponsor bliblablo" /> -->
         <sponso02 class="sponsor boxer" />
         <sponso03 class="sponsor heig" />
         <sponso04 class="sponsor impactvision" />
         <sponso05 class="sponsor infomaniak" />
         <sponso06 class="sponsor poste" />
         <sponso07 class="sponsor travys" />
         <sponso08 class="sponsor yverdon" />
         <!-- <sponso09 class="sponsor elca" /> -->
      </div>
      </div>
      <div class="row">
         <div class="copyright">
            <p>&copy; Baleinev 2025</p>
            <a href="mailto:info@baleinev.ch?subject=Demande depuis le site baleinev.ch" class="link">info@baleinev.ch</a>
         </div>
      </div>
     </div>
   </footer>
</template>

<style scoped lang="scss">
@use "./assets/css/main.scss" as *;
   footer {
      margin-top: auto;
      padding: $space-lg $space-sm $space-sm;      
   }

   .sponsor-container {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: $space-md;
      padding-top: $space-lg;
      border-top: 1px solid $color-white;

      @media(min-width: 768px) {
         gap: $space-lg;
      }
   }

   .sponsor {
      width: auto;
      height: 48px;
      align-self: center;
      max-width: calc(50% - #{$space-md});

      @media(min-width: 768px) {
         max-width: initial;
      }

      &.elca {
         height: 36px;
      }

      &.bliblablo,      
      &.heig{
         height: 64px;
      }

      &.yverdon,
      &.boxer {
         height: 80px;
      }
   }

   .copyright {
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-top: $space-lg;
   }
</style>