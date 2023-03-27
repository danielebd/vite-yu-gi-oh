
<script>
export default {
    name: 'Card',
    props: {
        img: String,
        name: String,
        archetype: String
    }
}
</script>

<template>
    <div class="card mb-3">
        <div class="img">
            <img :src="img" alt="">
        </div>
        <div class="name text-center text-light fw-bold py-2">
            {{ name }}
        </div>
        <div class="archetype text-center pb-2">
            {{ archetype }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .card {
        width: calc(100% / 5 - 15px);
        background-color: #d48f38;
        img {
            width: 100%;
        }
    }
</style>