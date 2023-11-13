<template>
    <main>
        <!--cards-->
        <div>
            <div class=" container-fluid bg-my-orange p-5 ">
                <div class="container py-5 bg-light  rounded-4 ">
                    <div class="row justify-content-center ">
                        <CardComponent v-for="(info,index) in cards" :key="index" :img="info.card_images[0].image_url" :name="info.name" :race="info.race" :type="info.type"/>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import CardComponent from './subcomponents/CardComponent.vue';
import { store } from '../assets/data/store.js';
export default {
    name: 'MainComponent',
    components: { 
        CardComponent,
    },
    data() {
        return {
            store, 
            cards: store.cardList
        }
    }
}
</script>

<style lang="scss" scoped>


</style>