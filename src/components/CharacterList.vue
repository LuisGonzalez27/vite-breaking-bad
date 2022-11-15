<template>
    <div class="container">
        <div class="row">
            <div class="col" v-for="(item, index) in store.characterList" :key="item.id">
                <CardComponent :character="item" />
            </div>
        </div>
    </div>
</template>

<script>
import { store } from "../store";
import CardComponent from './CardComponent.vue';
export default {
    components: { CardComponent },
    data() {
        return {
            store,
        };
    },
};
</script>

<style lang="scss" scoped>
.row {
    background-color: white;

    .col {
        flex-basis: calc(100% / 6);
        padding-top: 20px;
    }
}
</style>