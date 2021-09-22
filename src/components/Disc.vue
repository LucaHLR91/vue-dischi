<template>
  <div class="disc text-center">
      <img class="img-fluid mb-3" :src="info.poster" :alt="info.title">
      <h3>{{info.title}}</h3>
      <p>{{info.author}}</p>
      <p>{{info.year}}</p>
  </div>
</template>

<script>
export default {
    name: "Disc",
    props: ["info"]
}
</script>

<style lang="scss" scoped>
    @import '../style/General';
    .disc {
        display: flex;
        flex-direction: column;
        background-color: $primary-color;

        img {
            padding: 30px;
        }

        h3 {
            font-size: 25px;
            font-weight: 700;
            color: $title-color;
        }

        p {
            color: #77746B;
            font-size: 16px;
            font-weight: 700;
        }
    }
</style>