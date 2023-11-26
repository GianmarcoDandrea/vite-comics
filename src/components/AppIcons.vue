<script>
export default{
    data() {
        return{
            iconList : [
                {
                    name:"buy-comics-digital-comics.png",
                    text:"digital comics"
                },
                {
                    name:"buy-comics-merchandise.png",
                    text:"dc merchandise"
                },
                {
                    name:"buy-comics-subscriptions.png",
                    text:"subscrition"
                },
                {
                    name:"buy-comics-shop-locator.png",
                    text:"comic shop locator"
                },
                {
                    name:"buy-dc-power-visa.svg",
                    text:"dc power visa"
                },
            ]
        }
    },

    methods: {
        getImagePath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href
        }
    }
};

</script>

<template>
    <section>
        <div class="small-container">
            <div v-for="icon in iconList" class="card">

                <img :src="getImagePath(`${icon.name}`)" alt="">
                <a href="" class="icon-text">{{ icon.text }}</a>

            </div>
        </div>
    </section>

</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

section {
    background-color: $main-color;
    padding: 2rem 1rem;
}

.small-container {
    @include flex (row, space-between, center);
    gap: 1rem;
}

.card {
    @include flex(row, center, center);
    height: 100%;
    width: calc(100% / 5);
    padding: 1rem 0;

    &:last-child {
        img {
            width: 45%;
        }
    }

    img {
        height: 4.5rem;
        margin-right: 0.3rem;
    }
}

.icon-text {
    text-transform: uppercase;
    font-size: 0.75rem;
    color: $dark_section_text_color;
    text-decoration: none;
}
</style>