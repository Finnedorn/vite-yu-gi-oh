<template>
    <div>
        <select v-model="activeSelect" @change="$emit('filterSelect', activeSelect)" class="form-select" aria-label="Default select example">
            <option value="">...</option>
            <option value="-Eyes Dragon">-Eyes Dragon</option>
            <option value="Ancient Gear">Ancient Gear</option>
            <option value="Arcana Force">Arcana Force</option>
            <option value="Archfiend">Archfiend</option>
            <option value="Barbaros">Barbaros</option>
        </select>
    </div>
</template>

<script>
    export default {
        name:'SelectComponent',
        data() {
            return {
                activeSelect: '',
            }
        },
    }
</script>

<style lang="scss" scoped>
</style>