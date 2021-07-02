<template>
    <div id="app">
        <div class="title">Twitch hover effect examples</div>

        <div class="divider"></div>

        <section class="cards">
            <section class="cards__iterated">
                <twitch-hover v-for="(card, key) in cards"
                              :width="card.width"
                              :height="card.height"
                              :substrate-color="card.substrateColor"
                              :card-color="card.cardColor" :key=key></twitch-hover>
            </section>

            <div class="divider"></div>

            <section class="cards__custom">
                <twitch-hover
                        :image-src="'https://i.imgur.com/nTLC53I.png'"
                        :width="300"
                        :substrate-color="'#01f1c0'"
                        :duration="0.3"
                        :timing-function="'ease-in-out'"
                        :card-color="'blue'"></twitch-hover>
                <twitch-hover
                        :image-src="'http://cdn.shopify.com/s/files/1/0029/8198/6413/products/NLBCoolPink_1800x1800.jpg?v=1554576538'"
                        :height="200"
                        :substrate-color="'#dcb0dd'"
                        :card-color="'pink'"></twitch-hover>
                <twitch-hover
                        :image-src="'https://steamuserimages-a.akamaihd.net/ugc/949590558702165309/B700E129E73B8BD33AF045A37BD6928582EACB44/'"
                        :width="500"
                        :substrate-color="'#fea708'"
                        :card-color="'yellow'"></twitch-hover>
            </section>
        </section>
    </div>
</template>

<script>

    import TwitchHover from "@/components/TwitchHover"

    export default {

        name: 'app',
        components: {
            TwitchHover
        },
        data() {
            return {
                cards: [
                    {width: 250, height: 400, substrateColor: 'black', cardColor: 'yellow'},
                    {width: 250, height: 400, substrateColor: '#4fc3f7', cardColor: 'pink'},
                    {width: 250, height: 400, substrateColor: 'orange', cardColor: 'gray'},
                    {width: 250, height: 400, substrateColor: 'lightgreen', cardColor: '#ea80fc'},
                    {width: 250, height: 400, substrateColor: '#ffecb3', cardColor: '#ff8a65'},
                    {width: 250, height: 400, substrateColor: '#c5cae9', cardColor: '#4fc3f7'},
                ]
            }
        }
    }
</script>

<style lang="sass">
    @import url('https://fonts.googleapis.com/css?family=Cinzel&display=swap')

    #app, body, html
        padding: 0
        margin: 0
        max-height: 100%

        *
            box-sizing: border-box

        #app
            display: flex
            flex-direction: column
            justify-content: center
            align-items: center

            .divider
                width: 60%
                height: 0
                border-bottom: 1px solid darkgray

            .title
                font-family: 'Montserrat', serif
                margin-top: 20px
                font-size: 2.5rem
                font-weight: 500

            .cards
                height: 100%
                display: flex
                flex-direction: column
                align-items: center

                &__iterated
                    margin: 30px 0
                    display: flex
                    flex-wrap: wrap
                    flex-direction: row
                    justify-content: center
                    align-items: center

                    & > div
                        margin: 10px

                &__custom
                    margin-top: 30px
                    width: 100%
                    display: flex
                    flex-wrap: wrap
                    flex-direction: row
                    justify-content: space-around
                    align-items: center

                    & > div
                        margin: 10px

</style>
