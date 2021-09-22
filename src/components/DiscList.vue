<template>
  <main>
      <div class="container">
          <div class="row">
              <div v-for="(disc, index) in discList" :key="index" class="col-6 col-md-4 col-lg-3 mb-5">
                  <Disc :info= disc />
              </div>
          </div>
      </div>
  </main>
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
export default {
    name: "DiscList",
    components: {
        Disc
    },
    data() {
        return {
           APIurl: 'https://flynn.boolean.careers/exercises/api/array/music',
           discList: [] 
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