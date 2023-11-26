<script>
export default {
    data() {
        return {
            comics: [
                {
                    "thumb": "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                    "price": "$19.99",
                    "series": "Action Comics",
                    "type": "comic book"
                },
                {
                    "thumb": "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                    "price": "$3.99",
                    "series": "American Vampire 1976",
                    "type": "comic book"
                },
                {
                    "thumb": "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                    "price": "$16.99",
                    "series": "Aquaman",
                    "type": "graphic novel"
                },
                {
                    "thumb": "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                    "price": "$2.99",
                    "series": "Batgirl",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                    "price": "$3.99",
                    "series": "Batman",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                    "price": "$2.99",
                    "series": "Batman Beyond",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
                    "price": "$3.99",
                    "series": "Batman/Superman",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                    "price": "$4.99",
                    "series": "Batman/Superman Annual",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                    "price": "$5.99",
                    "series": "Batman: The Joker War Zone",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                    "price": "$6.99",
                    "series": "Batman: Three Jokers",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                    "price": "$4.99",
                    "series": "Batman: White Knight Presents: Harley Quinn",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg/revision/latest?cb=20160303223223",
                    "price": "$16.99",
                    "series": "Catwoman",
                    "type": "graphic novel"
                }]
        }
    },
    methods: {
        getImagePath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href
        }
    },

    components : {ComicsCard},
};

</script>

<template>
    <div class="jumbotron"></div>

    <section>
        <div class="container">

            <div class="current-title">
                <h3>
                    CURRENT SERIES
                </h3>
            </div>

            <div class="row">
                <div class="col" v-for="comic in comics">
                    <ComicsCard />
                </div>
            </div>
        </div>
    </section>

</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.jumbotron {
    height: 23rem;
    background-image: url(../assets/img/jumbotron.jpg);
    background-size: cover;
}


section {
    background-color: $dark_section_bg_color;

    .container {
        position: relative;
        padding: 2rem 0;
        background-color: $dark_section_bg_color;
        .current-title{
            color: $dark_section_text_color;
            background-color: $main_color;
            padding: 1rem 1.5rem;
            position: absolute;
            top: 0;
            left: -10px;
            transform: translateY(-50%); 
        }

        .row {
            padding: 1rem 0;
            color: $dark_section_text_color;
            @include flex (row, center, center, wrap);

            .col {
                width: calc(100% / 6);
                // debug
                padding: 3rem;
                border: 1px solid white;
            }

        }

    }
}
</style>