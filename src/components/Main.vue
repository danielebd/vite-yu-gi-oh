
<script>
import Archetype from './Archetype.vue';
import TabCards from './TabCards.vue'
export default {
    name: 'Main',
    components: {
        Archetype,
        TabCards

    }
}
</script>

<template>
    <main>
        <div class="my-container">
            <TabCards />
        </div>

    </main>
</template>
<style lang="scss" scoped>
main {
    background-color: #d48f38;

    .my-container {
        width: 1340px;
        margin: 0 auto;
        
    }
}
</style>