<script>
export default{
    props: {
        image: String,
        title: String,
    },

};

</script>

<template>
    <div class="card">
        <img :src="image" alt="">
        <h2 class="comic-title"> {{ title }}</h2>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.card {
    .comics-title {
        text-transform: uppercase;
        color: $dark_section_text_color;
    }
}

</style>