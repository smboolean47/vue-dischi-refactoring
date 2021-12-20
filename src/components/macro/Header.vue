<template>
    <header class="d-flex justify-content-between ps-3 pe-3">
        <div>
            <img src="../../assets/img/spotify-logo.png" alt="Spotify" />
        </div>
        <div>
            <SelectGenre/>
        </div>
    </header>
</template>

<script>
import SelectGenre from '../commons/SelectGenre.vue';

export default {
    name: "Haeder",
    components: {
        SelectGenre
    }
};
</script>

<style lang="scss" scoped>
header {
    height: 70px;
    background-color: #2e3a46;
    line-height: 70px;
    img {
        width: 50px;
    }
}
</style>