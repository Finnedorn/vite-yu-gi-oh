<template>
    <div class="mt-5 bg-my-orange">
        <div class="loading-page m-auto text-center p-5 ">
            <div class="loading-logo-wrapper p-2 ">
                <img src="../assets/images/yu_gi_oh__tcg_logo_by_homoco9_ddyvtrd-fullview.png" alt="yu-gi-oh_logo">
            </div>
            <div class="whitebar rounded-4 mt-5"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'LoadingScreenComponent',
        data() {
            return {
            }
        },
    }
</script>

<style lang="scss" scoped>

.loading-page {
    width: 570px;
}

.loading-page>div>i,h1 {
    font-size: 5rem;
    color: var(--color-headers);
}

.loading-page>div>i {
    animation-duration: 3s;
    animation-name: chat;
    animation-fill-mode: forwards;
}

@keyframes chat {
    from {transform: rotate(0deg);}
    to {transform: rotate(20deg);}
}

.whitebar {
    background-color: rgba(215, 215, 215, 0.688);
    height: 10px;
    width: 0%;
    animation-name: bar;
    animation-duration: 5s;
    animation-iteration-count: infinite;
}

@keyframes bar {
    from {width: 0%;}
    to {width: 100%;}
}

.loading-logo-wrapper {
    width: 500px;
}

</style>