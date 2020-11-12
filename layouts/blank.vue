<template>
    <v-app class="gradient-play" :style="image">
    <div>
      <nuxt />
    </div>
    </v-app>
</template>
<script>
    import bikeImg from "../assets/BG.png";
    export default {
    data() {
        return {
        image: { backgroundImage: `url(${bikeImg})` },
        };
    }
    };
</script>
<style scoped>
.gradient-play {
  background: #363062;
  background-size: 100%;
}
</style>