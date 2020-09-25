<template>
  <div>
  <!--search button -->
  <input type="text" v-model ="textSearch " />
  <b-button @click="searchData()" variant="info">search</b-button> <br> <br>
  <!--{{List}}-->
  <b-card-group columns>
  <b-card
  v-for="data in List" :key="data.mal_id"
    :title="data.title"
    :img-src="data.image_url"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
      {{data.synopsis}}
    </b-card-text>
    <b-button :href="data.url" pill variant="outline-info">Link.</b-button>
  </b-card>
  </b-card-group>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      List: null,
      textSearch: "",
    };
  },

  methods: {
    searchData() {
      axios
        .get("https://api.jikan.moe/v3/search/anime?q=" +this.textSearch+"page=1")
        .then((response) => {
          this.List = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
</style>