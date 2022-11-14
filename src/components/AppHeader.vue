<template>
    <header>
        <div class="title">
            <img class="logo" src="/img/bad.png" alt="Logo">
            <h1 class="my-5"> {{ title }}</h1>
        </div>
    </header>
</template>

<script>
export default {
    name: 'AppHeader',
    props: {
        title: String
    }
}
</script>

<style lang="scss" scoped>
.title {
    height: 100px;
    display: flex;
    align-items: center;
    padding-left: 20px;
}

h1 {
    color: white;
}

.logo {
    height: 40px;
}
</style>