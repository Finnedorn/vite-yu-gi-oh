<template>
    <div class="col-2 ms-1 py-1">
        <div>
            <img :src="img" :alt="name">
        </div>
        <div class=" text-center ">
            <h4 class=" fs-5 ">
                {{ name }}
            </h4>
            <h5 class=" fw-light ">
                {{ race }}
            </h5>
            <h5 class=" fs-6 fw-light ">
                {{ type }}
            </h5>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CardComponent',
        props: {
            img: String,
            name: String,
            race: String,
            type: String
        },
        data() {
            return {
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>