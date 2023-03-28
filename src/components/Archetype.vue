
<script>
export default {
    name: 'Archetype',
    props: {
        archetype: String,
        
    }
}
</script>

<template>
    <li><a class="dropdown-item" href="#">{{ archetype }}</a></li>
</template>

<style lang="scss" scoped>

</style>