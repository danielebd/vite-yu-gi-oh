
<script>
import axios from 'axios';
import { store } from '../store';
import TabCards from './TabCards.vue'
export default {
    name: 'Main',
    components: {
        TabCards
    },
    data() {
        return {
            store
        }
    },
    methods: {
        selected() {
            console.log('ciao');
            console.log(this.store.selectKey);
        },

        callCards() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php',
                {
                    params: {
                        archetype: this.store.selectKey
                    }
                })
                .then((response) => {
                    console.log(response);
                    this.store.cards = response.data.data;
                })
        }

    },
    created() {

            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')

                .then((response) => {
                    console.log(response);
                    this.store.archetypes = response.data;
                })
        
        this.callCards();
    }

}
</script>

<template>
    <main>
        <div class="my-container">
            <TabCards @select="callCards" />
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