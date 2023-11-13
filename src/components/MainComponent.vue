<template>
    <main>
    </main>
</template>

<script>
import CardComponent from './CardComponent.vue';
import { store } from '../assets/data/store';
export default {
    name: 'MainComponent',
    components: { CardComponent },
    data() {
        return {
            store
        }
    }
}
</script>

<style lang="scss" scoped>
</style>