<script>
import { objectToString } from '@vue/shared';

export default{
    props: {
        comic: Object,
    },

};

</script>

<template>
    <div class="card">
        <div class="comic-cover">
            <img :src="comic.thumb" alt="" class="cover">
        </div>
        <p class="comic-title"> {{ comic.series }}</p>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.card {
    width: 100%;
    margin-bottom: 1.5rem;
    .comic-cover {
        width: 100%;
        aspect-ratio: 1;

        .cover {
            width: 100%;
            aspect-ratio: 0.9;
            object-fit: cover;
            object-position: top;
        }
    }

    .comic-title {
        text-transform: uppercase;
        color: $dark_section_text_color;
        font-size: 0.9rem;
        margin-top: 0.5rem;
    }


}

</style>