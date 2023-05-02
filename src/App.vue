<script setup>
import { TMDB_API_KEY } from "./key.js";
import axois from "axios";
import { ref } from "vue";

const movieSelect = ref(null);
const movieData = ref(false);

const movieGet = async () => {
  movieData.value = (
    await axios.get(`https:api.themoviedb.org/3/movie/${movieSelect.value}}`, {
      params: {
        api_key: TMDB_API_KEY,
        append_to_response: "videos",
      },
    })
  ).data;
};
</script>
