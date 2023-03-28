
<script>
import Card from './Card.vue';
import Archetype from './Archetype.vue';
import axios from 'axios';
export default {
    name: 'TabCards',
    components: {
        Card,
        Archetype
    },
    data() {
        return {
            cards: [],
            result: 0,
            archetypes: [],
            selectKey: ""
        }
    },
    methods:{
        selected(){
            console.log('ciao');
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((response) => {
                console.log(response);
                this.cards = response.data.data;
            }),
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
            console.log(response);
            this.archetypes = response.data;
        })
    }

}
</script>

<template>
    <section class="big-container">
        <div class="dropdown p-4 my-archetype">
            <select onchange="selected()" class="form-select form-select-lg mb-3 my-select" aria-label=".form-select-lg example">
                <option  class="dropdown-item" value="">select archetype</option>
                <Archetype  v-for="element in archetypes.slice(15, 20)" :archetype="element.archetype_name" :value="element.archetype_name"/>
            </select>
        </div>
        <div class="my-container mx-auto py-5">
            <div class="n-files p-3">Found 39 Cards</div>
            <div class="cards-list d-flex flex-wrap">
                <Card v-for="(element, index) in cards.slice(0, 39)" :img="element.card_images[0].image_url"
                    :name="element.name" :archetype="element.archetype" v-show="(index = 39)" />
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.big-container {
    background-color: white;
    border: #d48f38;

    .my-archetype {
        background-color: #d48f38;
        .my-select{
            width: fit-content;
        }
    }

    .my-container {
        width: 1200px;

        .n-files {
            background-color: #212529;
            color: white;
        }
    }


}
</style>