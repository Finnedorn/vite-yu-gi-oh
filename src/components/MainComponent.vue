<template>
    <main>
        <!--cards-->
        <div>
            <div class="container py-5">
                <div class="d-flex flex-wrap  align-items-center justify-content-center py-3">
                    <div class="ms-4 pb-4" v-for="(info,index) in cards" :key="index">
                        <CardComponent :name="info.name" :race="info.race" :type="info.type"/>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import CardComponent from './subcomponents/CardComponent.vue';
import { store } from '../assets/data/store';
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

.img-wrapper {
    width: 50px;
    height: 50px;
}

</style>