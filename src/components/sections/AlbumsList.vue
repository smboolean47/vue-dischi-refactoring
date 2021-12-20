<template>
    <div>
        <div class="d-flex flex-wrap">
            <Disc v-for="(discItem, index) in discsFiltered" :key="index" :disc="discItem"/>
        </div>
    </div>
</template>

<script>
import dataShared from '../../share/dataShared';

import axios from "axios";
import Disc from "../commons/Disc";

export default {
    name: "AlbumsList",
    components: {
        Disc,
    },
    data() {
        return {
            dataShared,
            discs: [],
        };
    },
    created() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
                this.discs = res.data.response;

                this.discs.forEach(elm => {
                    if( dataShared.genres.includes(elm.genre) == false ) {
                        dataShared.genres.push(elm.genre);
                    }
                });
            })
            .catch((err) => {
                console.log(err);
            });
    },
    computed: {
        discsFiltered() {
            const discsFiltered = this.discs.filter( (elm) => {
                return elm.genre.includes(dataShared.genreSelected); // return true o false
            } );

            return discsFiltered;
        }
    }
};
</script>

<style>

</style>