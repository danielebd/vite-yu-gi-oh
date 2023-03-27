
<script>
export default {
    name: 'Header'
}
</script>

<template>
    <header class="d-flex align-items-center p-2">
        <div class="logo me-2">
            <img src="http://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="">
        </div>
        <h2>Yu-Gi-Oh Api</h2>
    </header>
</template>

<style lang="scss" scoped>
    header {
        .logo {
            width: 75px;
            img {
                width: 100%;
            }
        }
    }
</style>