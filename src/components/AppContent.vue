<script>
export default{
    data() {
        return{
            
        }
    }
};

</script>

<template>

    <section>

        <div class="container">
            <h2>--&gt; Content goes here &lt;--</h2>
        </div>

    </section>

</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

section {
    background-color: $dark_section_bg_color;
    height: 250px;
}

.container {
    height: 100%;
    @include flex (row, center, center);

    h2 {
        color: $dark_section_text_color;
    }
}

</style>