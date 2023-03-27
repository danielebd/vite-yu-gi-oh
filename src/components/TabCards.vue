
<script>
import Card from './Card.vue';
export default {
    name: 'TabCards',
    components: {
        Card
    }
}
</script>

<template>
    <section class="big-container">
        <div class="my-container mx-auto py-5">
            <div class="n-files p-3">Found 39 Cards</div>
            <div class="cards-list d-flex flex-wrap justify-content-between">
                <Card />
                <Card />
                <Card />
                <Card />
                <Card />
                <Card />
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.big-container {
    background-color: white;
    height: 1000px;

    .my-container {
        width: 1200px;
        
        .n-files {
        background-color: #212529;
        color: white;
    }
    }

    
}
</style>