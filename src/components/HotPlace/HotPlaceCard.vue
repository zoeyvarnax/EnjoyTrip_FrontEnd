<template>
  <v-card
    class="ma-4 pointer"
    max-width="374"
    @click="onClickHotPlaceCard(attraction.contentId)"
  >
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      height="250"
      :src="attraction.firstImage"
    ></v-img>

    <v-card-title>{{ attraction.title }}</v-card-title>

    <v-card-text>
      <p>{{ attraction.addr1 }}</p>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>
  </v-card>
</template>
<script>
export default {
  props: {
    attraction: Object,
  },
  data() {
    return {};
  },
  methods: {
    onClickHotPlaceCard(contentId) {
      this.$router.push({ name: "attraction", params: { contentId } });
    },
  },
};
</script>
<style scoped>
.pointer {
  cursor: pointer;
}
</style>