<template>
    <header class="site-header">
         <div class="site-header__wrapper">
            <img class="site-logo" alt="After Digital logo" src="@/assets/ad_logo.png" height="50">
            <nav class="navbar">
            <ul>
                <li><router-link to="/"><img alt="login" class="icon" src="@/assets/user.svg">Sign In</router-link></li>
                <li><router-link to="/"><img alt="basket" class="icon" src="@/assets/basket.svg">Basket</router-link></li>
            </ul>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style lang="scss" scoped>
@import "@/assets/styles/variables.scss";

.site-header {
    height: 180px;
    margin: 40px 20px;

    &__wrapper {
    background-color: $white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
  }
}

.site-logo {
    margin-left: 20px;
}

ul {  
    list-style-type: none;

    li {
        display: inline;
    }

    a {
        text-decoration: none;
    }
}

.icon {
    width: 2rem;
    height: auto;
}

</style>