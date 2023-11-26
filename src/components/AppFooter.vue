<script>
export default{
    data() {
        return{
            linkList: [
                {
                    name:"dc comics",
                    linkItems:[
                        "Character", 
                        "Comics",
                        "Movies",
                        "TV",
                        "Games",
                        "Videos",
                        "News"]
                },
                {
                    name:"shop",
                    linkItems:[
                        "Shop Dc", 
                    "Shop DC Collectible"]
                },
                {
                    name:"dc",
                    linkItems:[
                        "Term Of Use",
                        "Privacy Policy (New)",
                        "Ad Choices",
                        "Advertising",
                        "Jobs",
                        "Subscribtions",
                        "Talent Workshop",
                        "CPSC Certificates",
                        "Ratings",
                        "Shop Help",
                        "Contact Us"]
                },
                {
                    name:"sites",
                    linkItems:[
                        "DC",
                    "MAD Magazine", 
                    "DC Kids", 
                    "DC Universe", 
                    "DC Power Visa"]
                }
            ],

            socialIcon: [
                "footer-facebook.png",
                "footer-periscope.png",
                "footer-pinterest.png",
                "footer-twitter.png",
                "footer-youtube.png",
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
    <footer>
        <div class="footer-top">
    
            <div class="container">
                
                <div class="left-section">
                    
                    <div class="link-section">
                        
                        <div class="link-card" v-for="list in linkList">
                            <h3 class="list-title">{{ list.name }}</h3>
        
                            <ul>
                                <li v-for="(link) in list.linkItems">
                                    <a href="">{{link}}</a>
                                </li>
                            </ul>
                            
                        </div>
    
                    </div>
                </div>
                <div class="right-section">
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <div class="container">

                <div class="left-sct">
                    <a href="" class="sign-up-btn">
                        SIGN UP NOW!
                    </a>
                </div>

                <div class="right-sct">
                    <h3 class="follow-title">
                        FOLLOW US!
                    </h3>

                    <ul>
                        <li v-for="icon in socialIcon">
                            <a href="">
                                <img :src="getImagePath(`${icon}`)" alt="">
                            </a>
                        </li>
                    </ul>
                </div>

            </div>
        </div>

    </footer>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.footer-top {
    background-image: url(../assets/img/footer-bg.jpg);
    background-size: cover;
    height: 25rem;

    .container {
        @include flex(row, space-between, center);
        height: 100%;
        .left-section {
            padding: 2rem 0;
            width: 40%;
            height: 100%;
    
            .link-section {
                width: 100%;
                height: 100%;
                @include flex (column, flex-start, flex-start, wrap);
                .link-card {
                    margin-bottom: 2rem;
                    margin-right: 2rem;
                    .list-title {
                        text-transform: uppercase;
                        color: $dark_section_text_color;
                    }
        
                    ul {
                        list-style-type: none;
            
                        li {
                            margin: 0.35rem 0;
            
                            a {
                                text-decoration: none;
                                color: $secondary_text_color;
                            }
                        }
                    }
                }
            }
        }

        .right-section {
            width: 47%;
            height: 100%;
            background-image: url(../assets/img/dc-logo-bg.png);
            background-position: center;
            background-size: cover;
            background-repeat: no-repeat;
        }
    }
}

.footer-bottom {
    background-color: $footer_bg_color;
    .container {
        padding: 1.5rem 0;
        @include flex(row, space-between, center);
    
        .left-sct{
            @include flex(row, flex-start, center);
            .sign-up-btn {
                text-decoration: none;
                color: $footer_title_color;
                padding: 1rem;
                border: 2px solid $main-color;
            }
        }
    
        .right-sct{
            @include flex(row, flex-end, center);

            .follow-title {
                color: $main_color;
                font-family: $text_link_header;
            }
            
            ul {
                @include flex(row, flex-end, center);
                list-style-type: none;
    
                li {
                    margin-left: 2rem;
                }
            }
        }
    }
}
</style>