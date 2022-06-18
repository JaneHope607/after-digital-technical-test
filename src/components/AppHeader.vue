<template>
    <header>
        <img alt="After Digital logo" src="@/assets/ad_logo.png" height="50">
        <nav class="navbar">
            <ul>
                <li><router-link to="/"><img alt="login" src="@/assets/user.svg">Sign In</router-link></li>
                <li><router-link to="/"><img alt="basket" src="@/assets/basket.svg">Basket</router-link></li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style lang="scss">

</style>