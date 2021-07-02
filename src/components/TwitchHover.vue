<template>
  <div class="tw-lift"
       :style="{
          width: width + 'px',
          height: height + 'px'
        }">
    <div class="tw-lift__card"
         :style="{
            backgroundColor: cardColor,
            transitionDuration: duration + 's',
            transitionTimingFunction: timingFunction
          }">
      <img v-if="imageSrc" alt="" :src="imageSrc" class="tw-lift__card__image"/>
    </div>
    <div class="tw-lift__substrate"
         :style="{
            backgroundColor: substrateColor
          }">
    </div>
    <div class="tw-lift__corner tw-lift__corner--top-left"
         :style="{
            borderRightColor: substrateColor,
            transitionDuration: duration + 's',
            transitionTimingFunction: timingFunction
          }">
    </div>
    <div class="tw-lift__corner tw-lift__corner--bottom-right"
         :style="{
            borderTopColor: substrateColor,
            transitionDuration: duration + 's',
            transitionTimingFunction: timingFunction
         }">
    </div>
  </div>
</template>

<script>
export default {
  name: "TwitchHover",
  props: {
    'substrateColor': {type: String, default: 'deeppink'},
    'cardColor': {type: String, default: 'blue'},
    'width': {type: Number, default: 200},
    'height': {type: Number, default: 300},
    'imageSrc': {type: String, default: null},
    'duration': {type: Number, default: 0.1},
    'timingFunction': {
      type: String, default: 'ease',
      validator(value) {
        return ['ease', 'ease-in', 'ease-out', 'ease-in-out', 'linear'].indexOf(value) !== 1
      }
    }
  },
}
</script>

<style scoped lang="sass">
$lift: 10px
$timeFunction: .1s
$cardWidth: 200px
$cardHeight: 300px

.tw-lift
  position: relative

  &:hover
    .tw-lift__card
      transform: translate($lift, -$lift)

    .tw-lift__corner--top-left
      transform: translateY(-$lift*2) scale(1)

    .tw-lift__corner--bottom-right
      transform: translateX($lift*2) scale(1)

  &__card
    width: 100%
    height: 100%
    position: absolute
    z-index: 2
    transition-property: transform
    display: flex
    flex-direction: row
    justify-content: center
    align-items: center

    &__image
      object-fit: cover
      width: 100%
      height: 100%

  &__substrate
    width: 100%
    height: 100%
    position: absolute
    left: 0
    top: 0
    z-index: 1

  &__corner
    position: absolute
    width: 0
    height: 0
    transition-property: transform

  &__corner--top-left
    top: $lift
    left: 0
    border-bottom: $lift solid transparent
    border-right: $lift solid deeppink
    border-top: $lift solid transparent
    transform-origin: left center
    transform: translateY(-$lift*2) scale(0)

  &__corner--bottom-right
    right: $lift
    bottom: 0
    border-left: $lift solid transparent
    border-right: $lift solid transparent
    border-top: $lift solid deeppink
    transform-origin: bottom center
    transform: translateX($lift*2) scale(0)
</style>
