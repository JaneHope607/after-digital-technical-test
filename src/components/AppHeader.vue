<template lang="html">
    <header class="site-header">
         <div class="site-header__wrapper">
            <img class="site-logo" alt="After Digital logo" src="@/assets/ad_logo.png">
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
    name: 'app-header'
}
</script>

<style lang="scss" scoped>
@import "@/assets/styles/variables.scss";

.site-header {
    max-height: 180px;
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
    max-height: 35px;
    width: auto;
}

ul {  
    list-style-type: none;

    li {
        display: inline;
    }

    a {
        text-decoration: none;
        color: inherit;
        margin: 0.5rem
    }
}

.icon {
    width: 1rem;
    height: auto;
    margin-right: 0.5rem
}

@media (max-width: $mobile-width) {
    .site-logo{
        max-height: 25px;
    }

    ul li {
        display: block;
    }
}

</style>