<template>
    <div class="container">
        <select class="form-select mb-3 category" aria-label="Default select example">
            <option selected>Select Category</option>
            <option value="1">Breaking Bad</option>
            <option value="2">Status</option>
        </select>
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
.category {
    width: 160px;
}

.row {
    background-color: white;

    .col {
        flex-basis: calc(100% / 6);
        padding-top: 20px;
    }
}
</style>