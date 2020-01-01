<template>
    <header class="app-head">
        <img v-if="app.avatarUri" class="app-icon" :alt="app.displayName" :src="app.avatarUri">
        <img v-else class="app-icon" src="https://firebasestorage.googleapis.com/v0/b/darpg-qkaecm.appspot.com/o/pglogo.png?alt=media&token=b9972ab7-c0dd-48ba-91eb-eb50d3771755" :alt="app.displayName">

        <slot />
    </header>
</template>

<style lang="sass" scoped>
@import './../App/Mixins.sass'

.app-head
    z-index: 666
    padding: 16px
    position: fixed
    width: 100%
    background-color: var(--background)

    .app-icon
        border-radius: 8px
        width: 20%
        height: 50%
        object-fit: cover
        background-color: var(--image-background)

    .app-info
        display: inline-block
        margin-left: 10px

        .app-name
            font-size: 18px
            font-weight: 500
            color: var(--text)

        .app-poweredby
            color: var(--text-secondary)
            font-size: 14px

            a[href]
                color: var(--text)
                text-decoration: none

.audio-toggle
    @include reset
    display: flex
    position: fixed
    top: 0
    right: 0
    margin: 16px 0
    z-index: 999
    padding: 8px 8px 8px 8px
    background-color: var(--element-background)
    border-radius: 20px 0 0 20px
    cursor: pointer
    color: var(--text)
    transition: padding .25s ease

    &:hover
        padding-right: 20px
</style>

<script>
export default {
    name: 'TopHead',
    props: {
        app: {
            type: Object,
            default: null
        }
    }
}
</script>