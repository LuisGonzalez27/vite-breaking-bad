<template>
    <div class="container">
        <div class="row">
            <div class="col" v-for="(item, index) in characters" :key="item.id">
                <CardComponent :character="item" />
            </div>
        </div>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
    name: "CharacterList",
    props: ["characters"],
    components: { CardComponent }
}
</script>

<style lang="scss" scoped>
.row {
    background-color: white;

    .col {
        flex-basis: calc(100% / 6);
    }
}
</style>