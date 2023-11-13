<template>
    <div class="card-wrapper">
        <div class="img-card-wrapper">
            <img :src="img" :alt="name">
        </div>
        <div class=" text-center ">
            <h3 class="pt-3">
                {{ name }}
            </h3>
            <h5 class="pt-3 fw-light ">
                {{ race }}
            </h5>
            <h5 class="pt-3 fw-light ">
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
.img-card-wrapper {
    border-radius: 50%;
    height: 200px;
    overflow: hidden;
}
</style>