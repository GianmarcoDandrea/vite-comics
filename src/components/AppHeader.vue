<script>
export default{
    data() {
        return {
            navItem : [
                "character",
                "comics",
                "movies",
                "tv",
                "games",
                "collectibles",
                "videos",
                "fan",
                "news",
                "shop",
            ]
        }
    }
};
</script>

<template>
    <header class="container">
        <div class="logo">
            <img src="../assets/img/dc-logo.png" alt="">
        </div>

        <nav class="navbar">
            <ul>
                <li v-for="item in navItem">
                    <a href="">{{ item }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
    .container {
        @include flex("","", stretch);
    }

    .logo {
        padding: 0.5rem 0;
    }

    header {
        @include flex(row, space-between, center);
    }

    .navbar {
        @include flex (row, center, stretch);

        ul {
            @include flex (row, center, center);
            list-style-type: none;
            gap: 1.5rem;
            font-size: 0.9rem;
            font-weight: bold;

            li {
                @include flex(row, center , center);
                position: relative;
                height: 100%;
                
                a {
                    text-decoration: none;
                    color: #000000;
                    text-transform: uppercase;
                }
    
                &::after {
                    content: "";
                    width: 100%;
                    background-color: $main_color;
                    position: absolute;
                    left: 0;
                    bottom: 0;
                }

                &:hover {
                    a {
                        color: $main-color;
                    }
                    &::after {  
                        height: 5px;
                    }

                    
                }
    
            }
        }
    }

</style>