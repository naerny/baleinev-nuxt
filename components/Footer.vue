<script setup>
import sponso01 from '../assets/svg/sponsors/bliblablo.svg'
import sponso02 from '../assets/svg/sponsors/boxer.svg'
import sponso03 from '../assets/svg/sponsors/heig.svg'
import sponso04 from '../assets/svg/sponsors/impactvision.svg'
import sponso05 from '../assets/svg/sponsors/infomaniak.svg'
import sponso06 from '../assets/svg/sponsors/poste.svg'
import sponso07 from '../assets/svg/sponsors/travys.svg'
import sponso08 from '../assets/svg/sponsors/yverdon.svg'
</script>

<template>
   <footer>      
     <div class="container">
      <div class="sponsor-container">
         <sponso01 class="sponsor bliblablo" />
         <sponso02 class="sponsor boxer" />
         <sponso03 class="sponsor heig" />
         <sponso04 class="sponsor impactvision" />
         <sponso05 class="sponsor infomaniak" />
         <sponso06 class="sponsor poste" />
         <sponso07 class="sponsor travys" />
         <sponso08 class="sponsor yverdon" />
      </div>
     </div>
   </footer>
</template>

<style scoped lang="scss">
@use "./assets/css/main.scss" as *;
   footer {
      margin-top: auto;
      padding: $space-lg 0;      
   }

   .sponsor-container {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: $space-lg;
      padding-top: $space-lg;
      border-top: 1px solid $color-white;
   }

   .sponsor {
      width: auto;
      height: 48px;
      align-self: center;

      &.bliblablo,
      &.boxer,
      &.heig{
         height: 64px;
      }

      &.yverdon {
         height: 80px;
      }
   }
</style>