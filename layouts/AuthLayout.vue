<template>
<div>
    <Loader />
    <section class="sign-in-page">
        <nuxt />
    </section>
</div>
</template>

<script>
import Loader from '../components/core/loader/Loader'
import logo from '../assets/images/logo.png'
import { core } from '../assets/app/app'
export default {
    name: 'AuthLayout',
    components: {
        Loader
    },
    data() {
        return {
            options: {
                slidesPerView: 1,
                loop: true
            }
        }
    },
    mounted() {
        core.index()
    }
}
</script>

<style>
@import url('../assets/css/custom.css');
/* @import url('../assets/css/backend/variable.css');
@import url('../assets/css/backend/dark.css');
@import url('../assets/css/backend/style.css');
@import url('../assets/css/backend/typography.css'); */
@import url('../assets/css/frontend/variable.css');
@import url('../assets/css/frontend/dark.css');
@import url('../assets/css/backend/style.css');
@import url('../assets/css/frontend/typography.css');
@import url('../assets/css/mine.css');
</style>
