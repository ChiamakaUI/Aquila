<template>
  <div>
    <div class="mainBg">
        <div class="backgroundOne"></div>
        <div class="backgroundTwo"></div>
    </div>
    <div style="zIndex: 1;">
        <h1 id="headerName">{{ main.name }}</h1>
        <ul class="list">
            <li style="margin: 10px;">
                <a class="icon" v-bind:href="'twitter.com/'+ main.social_media.twitter">
                    <i class="fab fa-4x fa-twitter-square"></i>
                </a>
            </li>
            <li style="margin: 10px;">
                <a class="icon" v-bind:href="'instagram.com/'+ main.social_media.instagram">
                    <i class="fab fa-4x fa-instagram"></i>
                </a>
            </li>
            <li style="margin: 10px;">
                <a class="icon" v-bind:href="'snapchat.com/'+ main.social_media.snapchat">
                    <i class="fab fa-4x fa-snapchat-square"></i>
                </a>
            </li>
            <li style="margin: 10px;">
                <a class="icon" v-bind:href="'mailto:'+ main.social_media.email">
                    <i class="far fa-4x fa-envelope"></i>
                </a>
            </li>
        </ul>
    </div>
  </div>

</template>

<script>
    import axios from "axios";

    export default {
        name: "Main",
        data() {
            return {
                main: null,
            };
        },
        created: function () {
            axios.get("https://hirng-x2021.glitch.me/api").then((res) => {
                this.main = res.data;
            });
        },
    };
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Dosis:wght@300&display=swap');

    .mainBg {
        position:fixed; 
        height: 100%; 
        z-Index: -1;
    }

    .backgroundOne {
        background-color: #BD0F4D;
        height: 100%;
        width: 50%; 
        position: fixed;
        left: 0;
    }

    .backgroundTwo {
        background-color: #CB2964;
        height: 100%;
        width: 50%; 
        position: fixed;
        right: 0;
    }


    #headerName {
        font-family: 'Dosis';
        margin-top: 50px;
        color: white;
        letter-spacing: 10px;
    }

    .icon {
        color: white;
    }

    .list {
        position: fixed; 
        right: 10px; 
        bottom: 10px;
        list-style: none;
    }
</style>
