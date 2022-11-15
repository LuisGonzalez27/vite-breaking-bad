<template>
    <div class="container d-flex justify-content-center p-4">
        <form class="row row-cols-lg-auto g-3 align-items-center" @submit.prevent="searchCharacters"
            @reset="resetSearch">
            <div class="col-12">
                <select class="form-select" name="category" id="category" v-model="store.search.category">
                    <option selected value="">Serie</option>
                    <option :value="category" v-for="(category, index) in categoryAPI" :key="index">
                        {{ category }}
                    </option>
                </select>
            </div>

            <div class="col-12">
                <button type="submit" class="btn btn-primary">Search</button>
            </div>

            <div class="col-12">
                <button type="reset" class="btn btn-primary">Reset</button>
            </div>
        </form>
    </div>
</template>
  
<script>
import { store } from "../store";

export default {
    name: "SearchComponent",
    data() {
        return {
            store,
            categoryAPI: [
                "Breaking Bad",
                "Better Call Saul"
            ],
        };
    },
    methods: {
        searchCharacters() {
            this.$emit("filteredChar");
        },
        resetSearch() {
            store.search.category = "";
            this.$emit("filteredChar");
        },
    },
};
</script>

<style lang="scss" scoped>

</style>