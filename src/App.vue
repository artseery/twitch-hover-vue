<template>
    <div id="app">
        <twitch-hover :width="300" :height="400" :substrate-color="'black'" :card-color="'yellow'"></twitch-hover>
        <twitch-hover :image-src="'https://i.imgur.com/nTLC53I.png'" :width="300" :substrate-color="'lightblue'" :card-color="'cyan'"></twitch-hover>
        <twitch-hover :image-src="'https://i.imgur.com/NTgYlGC.jpg'" :height="200" :substrate-color="'lightgray'" :card-color="'pink'"></twitch-hover>
    </div>
</template>

<script>

    import TwitchHover from "@/components/TwitchHover";

    export default {

        name: 'app',
        components: {
            TwitchHover
        }
    }
</script>

<style>
    #app, body, html {
        padding: 0;
        margin: 0;
        height: 100%;
    }

    * {
        box-sizing: border-box;
    }
    #app {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
    }
</style>
