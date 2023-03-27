
<script>
import Card from './Card.vue';
import axios from 'axios';
export default {
    name: 'TabCards',
    components: {
        Card
    },
    data() {
        return {
            cards: []
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then((response) => {
            console.log(response)
            this.cards = response.data.data;
        })
    }
}
</script>

<template>
    <section class="big-container">
        <div class="my-container mx-auto py-5">
            <div class="n-files p-3">Found 39 Cards</div>
            <div class="cards-list d-flex flex-wrap justify-content-between">
                <Card v-for="element in cards.slice(0,39)" :img="element.card_images[0].image_url" :name="element.name" :archetype="element.archetype"/>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.big-container {
    background-color: white;

    .my-container {
        width: 1200px;

        .n-files {
            background-color: #212529;
            color: white;
        }
    }


}
</style>