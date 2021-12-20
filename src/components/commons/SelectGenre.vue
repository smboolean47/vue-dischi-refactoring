<template>
    <select v-model="dataShared.genreSelected" class="form-select w-auto">
        <option value="">Seleziona un genere</option>
        <option v-for="(genre, index) in dataShared.genres" :value="genre" :key="index">{{genre}}</option>
    </select>
</template>

<script>
import dataShared from '../../share/dataShared';

export default {
    name: "SelectGenre",
    data() {
        return {
            dataShared
        }
    }
}
</script>

<style>

</style>