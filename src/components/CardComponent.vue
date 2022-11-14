<template>
    <div class="character">
        <img :src="character.img" :alt="character.name">
        <p>{{ character.name }}</p>
        <p>{{ character.status }}</p>
        <p>{{ character.nickname }}</p>
    </div>
</template>

<script>
export default {
    props: {
        character: Object
    }
}
</script>

<style lang="scss" scoped>
.character {
    width: 220px;

    img {
        width: 200px;
    }

}
</style>