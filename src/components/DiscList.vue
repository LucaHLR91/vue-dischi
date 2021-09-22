<template>
    <main>
        <div class="container">
            <div class="row" v-if="!loading">
                <div v-for="(disc, index) in discList" :key="index" class="col-6 col-md-4 col-lg-3 mb-5">
                    <Disc :info= disc />
                </div>
            </div>
            <Loader v-else />
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
import Loader from './Loader.vue';
export default {
    name: "DiscList",
    components: {
        Disc,
        Loader
    },
    data() {
        return {
           APIurl: 'https://flynn.boolean.careers/exercises/api/array/music',
           discList: [],
           loading: true 
        }
    },
    created() {
        this.getDiscs()
    },
    methods: {
        getDiscs() {
            axios.get(this.APIurl)
            .then(res => {
                console.log(res.data.response);
                this.discList = res.data.response
                this.loading = false;
                setTimeout( () => {this.loading = false; }, 5000);
            })
            .catch( err => {
            console.log("Error ", err);
          })
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/General';

    main {
        background-color: $secondary-color;
        padding: 50px;
    }
</style>