
<script>
export default {
    name: 'Archetype',
    props: {
        archetype: String,
        value: String
    }
}
</script>

<template>
    <option :value="value" class="dropdown-item">{{ archetype }}</option>
</template>

<style lang="scss" scoped>

</style>
