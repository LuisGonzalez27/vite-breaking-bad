<template>
    <div class="character" style="height: 460px;">
        <img :src="character.img" :alt="character.name" class="my-card-img">
        <div class="text-center">
            <h5>{{ character.name }}</h5>
            <div class="other-info">
                <p>{{ character.category }}</p>
                <p>{{ character.status }}</p>
            </div>
        </div>

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
@use '../assets/styles/partials/variables' as*;

.character {
    width: 220px;
    background-color: $graydark;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 10px;

    h5 {
        padding-top: 10px;
        color: white;
        text-transform: uppercase;
    }
}

.other-info {
    padding-top: 20px;
    line-height: 15px;

    p {
        color: gray;
    }
}
</style>