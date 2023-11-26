<script>
import AppHeader from './components/AppHeader.vue'
import AppContent from './components/AppContent.vue'
import AppIcons from './components/AppIcons.vue'
import AppFooter from './components/AppFooter.vue'

export default {
    components: {
        AppHeader,
        AppContent,
        AppIcons,
        AppFooter,
    }
}
</script>

<template>
    <AppHeader />
    <AppContent />
    <AppIcons />
    <AppFooter />

</template>

<style lang="scss">
@use "./style/general.scss";
</style>
