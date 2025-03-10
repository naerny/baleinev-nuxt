<script setup>
import { onMounted } from 'vue';

// onMounted(() => {
//   const script = document.createElement('script');
//   script.id = 'etickets';
//   script.src = 'https://infomaniak.events/scripts/shop/1JX2WZX23L';
//   const scriptContainer = document.getElementById('ticketing-script');
//   scriptContainer.appendChild(script);
// });
</script>

<template>
    <section class="section-ticketing section-margin" id="ticketing">
        <div class="container">
            <div class="row">
                <div class="col-12 col-lg-8 offset-lg-2">
                    <h2>Billeterie</h2>
                    <!-- <p class="h3">La billeterie ouvrira bientôt ses portes!</p>
                    <p>Stay tuned...</p> -->
                    <div class="ticketing__cta">
                        <div class="ticketing__ctaCopy">
                            <p class="h3">La billeterie est maintenant ouverte!</p>    
                            <p>Dépèche-toi pour obtenir ton billet <span><strong>early bird</strong></span>!<br>Disponible jusqu'au 3 mai.</p>                        
                        </div>
                        <a class="btn btn__primary btn__big"
                            href="https://infomaniak.events/fr-ch/shop/baleinev-festival-1JX2WZX23L" target="_blank"
                            rel="noopener">
                            J'achète mon billet!
                        </a>
                        
                    </div>
                    <!-- <div id="ticketing-script"></div> -->
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
@use "./assets/css/main.scss" as *;

.ticketing {
    &__cta {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: $space-sm;
        padding: $space-md;
        background: $color-white;
        border-radius: 1rem;

        p {
            color: $color-black;
            text-align: center;
        }

        span {
            color: $color-lila;
            font-family: 'Bebas Bold';
        }
    }

    &__ctaCopy {
        text-align: center;       
    }
}
</style>